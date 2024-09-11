---
layout: essay
type: essay
title: "Boas práticas no PowerShell"
# All dates must be YYYY-MM-DD format!
date: 2024-09-11
published: true
labels:
  - PowerShell
---

<img class="img-fluid" src="../img/Share.png">

Este script PowerShell automatiza a consulta de compartilhamentos de produção no ambiente HCM. Ele permite que o usuário verifique se as pastas específicas estão compartilhadas corretamente em um servidor remoto, filtrando por critérios personalizados, e apresenta um relatório detalhado de pastas compartilhadas e não compartilhadas.

Funcionalidades:
- Consulta remota: O script conecta-se a um servidor especificado pelo usuário e executa uma busca nas pastas de produção localizadas no disco D:.
- Filtros personalizados: As pastas são filtradas para que apenas aquelas com o padrão "_p" e sem os termos "OLD" ou "Teste" sejam verificadas.
- Validação de compartilhamento: O script verifica se essas pastas estão corretamente compartilhadas, excluindo compartilhamentos que não seguem os padrões de nome, como "OCSEN*", "_h", e outros.
- Relatório em tempo real: Exibe de forma clara se cada pasta encontrada está compartilhada ou não, utilizando cores para realçar as pastas que não estão compartilhadas.
- Loop interativo: Ao final da execução, o usuário pode optar por reiniciar o script ou encerrá-lo.

```
while ($true) {
    Clear-Host
    Write-Host "Script para consultar os compartilhamentos de PRODUÇÃO do HCM" -ForegroundColor Green

    # Define o nome do servidor remoto
    $nomeServidor = Read-Host "Qual servidor você deseja consultar o compartilhamento?"

    Write-Host "Realizando a consulta..." -ForegroundColor Yellow

    # Obtém a lista de pastas que atendem aos critérios
    $listaPastas = Invoke-Command -ComputerName $nomeServidor -ScriptBlock {
        Get-ChildItem -Path D:\* -Directory | Where-Object {$_.Name -like "*_p*" -and $_.Name -notlike "*OLD*" -and $_.Name -notlike "*Teste*"}
    }

    # Obtém todos os compartilhamentos do servidor remoto 
    $compartilhamentos = Get-WmiObject -ComputerName $nomeServidor -Class Win32_Share | Where-Object {$_.Path -like "D:\*" -and $_.Name -notlike "\\OCSEN*" -and $_.Name -notlike "*_h*" -and $_.Name -notlike "D$" -and $_.Name -notlike "*csmcenter*" -and $_.Name -notlike "*config*"}

    # Itera sobre cada pasta encontrada
    foreach ($pasta in $listaPastas) {
        $pastaCompartilhada = $false

        # Compara com cada compartilhamento
        foreach ($compartilhamento in $compartilhamentos) {
            if ($pasta.FullName -eq $compartilhamento.Path) {
                $pastaCompartilhada = $true
                break
            }
        }

        # Exibe se a pasta está compartilhada ou não
        if ($pastaCompartilhada) {
            Write-Host "A pasta $($pasta.Name) está compartilhada."
        } else {
            Write-Host "A pasta $($pasta.Name) não está compartilhada." -ForegroundColor Red
        }
    }

    # Laço de repetição
    $restartScript = Read-Host -Prompt "Deseja reiniciar o script? Sim(S) Não(N)"
    if ($restartScript -ne "S") {
        break
    }
}
```

Benefícios:
- Automatização: Evita a necessidade de checagens manuais, otimizando o tempo e minimizando erros.
- Segurança: Garante que apenas pastas relevantes estejam compartilhadas, ajudando na organização e segurança do ambiente de produção.
- Flexibilidade: O usuário pode consultar qualquer servidor de produção, o que o torna útil para diversos ambientes.
- Esse script é um exemplo prático de como o PowerShell pode ser utilizado para gerenciar e auditar compartilhamentos em servidores remotos de forma eficiente.
