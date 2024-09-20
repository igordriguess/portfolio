---
layout: project
type: project
image: img/project-image2.png
title: "Ferramenta de Gestão de Serviços"
date: 2024
published: true
labels:
  - Python
  - PowerShell
summary: "Aplicativo de automação em Python para execução de scripts em Powershell"
---

Este projeto consiste em uma interface gráfica (GUI) desenvolvida em Python, utilizando a biblioteca Tkinter, para manipulação remota de serviços em ambientes de Produção e Homologação de uma infraestrutura HCM SaaS da Senior. A ferramenta permite consultar, iniciar e parar serviços associados a um cliente específico, simplificando o gerenciamento de serviços em múltiplos servidores.

<b>Funcionalidades:</b> <br/>
Consulta de Serviços Remotos: A aplicação realiza consultas remotas para verificar o status de serviços utilizando comandos PowerShell através da função subprocess, apresentando os resultados em uma tabela interativa. <br/>
Ambientes Diferenciados: O usuário pode selecionar se deseja realizar a operação no ambiente de Produção ou Homologação, garantindo maior controle sobre os ambientes. <br/>
Filtragem de Serviços: A interface possui um sistema de filtragem onde os nomes reais dos serviços são mascarados com nomes descritivos. Por exemplo, um serviço identificado como "seniorinst" é apresentado ao usuário como "Senior Serviço de Informação da Instalação", facilitando a identificação. <br/>
Manipulação de Serviços: O usuário pode selecionar serviços específicos ou optar por manipular todos os serviços de uma vez. A partir desta seleção, ele pode iniciar ou parar os serviços diretamente da interface. <br/>

<b>Tecnologias utilizadas:</b> <br/>
Python 3: Linguagem principal usada no projeto. <br/>
Tkinter: Biblioteca nativa do Python para criação de interfaces gráficas. <br/>
subprocess: Módulo utilizado para execução de comandos PowerShell remotamente. <br/>
PowerShell: Linguagem de script para realizar consultas e operações nos servidores remotos. <br/>

<b>Interface do Usuário:</b> <br/>
Botões de Controle: O usuário pode consultar, iniciar ou parar serviços através de botões intuitivos. <br/>
Tabela Dinâmica: A tabela apresenta os resultados das consultas de serviços, mostrando o nome do serviço (mascarado) e o estado atual (Em Execução ou Parado). <br/>
Combobox Interativa: Um campo de seleção permite ao usuário escolher o serviço específico ou todos os serviços para realizar a operação desejada. <br/>

<b>Lógica do Script:</b> <br/>
Consulta de Serviços: Através do botão "Consultar Serviços", a aplicação coleta os serviços ativos no servidor remoto, aplicando filtros pelo cliente e ambiente selecionados. O comando PowerShell é executado remotamente, e os resultados são mostrados na tabela. <br/>
Iniciar/Parar Serviços: O usuário pode iniciar ou parar serviços individualmente ou em massa. Para isso, ele escolhe o serviço desejado no combobox e clica em "Iniciar Serviço(s)" ou "Parar Serviço(s)", acionando o comando PowerShell que realiza a ação no servidor remoto. <br/>

<b>Exemplo de uso:</b> <br/>
O administrador deseja verificar se todos os serviços de um cliente específico estão em execução no ambiente de Produção ou Homologação. Ele seleciona o ambiente "Produção", consulta os serviços e vê o status na tabela. <br/>
Se algum serviço estiver parado, ele pode iniciá-lo diretamente da interface. <br/>

<img class="img-fluid" src="../img/ServiceCloud.png">

Clique [aqui](https://github.com/igordriguess/ManipulaServicesCloud/blob/main/ManipulaServicesCloud.py) para visualizar o código completo.
