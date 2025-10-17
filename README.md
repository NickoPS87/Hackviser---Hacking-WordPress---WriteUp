# Write-Up: Hacking WordPress - Laboratório CWSE

## 🎯 Visão Geral do Laboratório

Este repositório contém o write-up detalhado para o desafio de segurança em WordPress do laboratório CWSE. O objetivo é documentar o processo de exploração de uma vulnerabilidade no plugin "Pie Register" para obter acesso administrativo, executar código remotamente (RCE) e, finalmente, capturar a flag encontrando a senha do banco de dados no arquivo `wp-config.php`.

## 📜 Sumário (Table of Contents)

- [Fase 1: Reconhecimento e Enumeração](#-fase-1-reconhecimento-e-enumeração)
  - [Escaneamento de Portas com Nmap](#escaneamento-de-portas-com-nmap)
  - [Enumeração do WordPress com WPScan](#enumeração-do-wordpress-com-wpscan)
- [Fase 2: Exploração da Vulnerabilidade](#-fase-2-exploração-da-vulnerabilidade)
  - [Identificando a Vulnerabilidade no Pie Register](#identificando-a-vulnerabilidade-no-pie-register)
  - [Explorando a Falha de Autenticação (Authentication Bypass)](#explorando-a-falha-de-autenticação-authentication-bypass)
  - [Obtendo o Cookie de Administrador](#obtendo-o-cookie-de-administrador)
- [Fase 3: Pós-Exploração e Escalação de Privilégios](#-fase-3-pós-exploração-e-escalação-de-privilégios)
  - [Acessando o Painel Administrativo](#acessando-o-painel-administrativo)
  - [Upload de Plugin Malicioso para RCE](#upload-de-plugin-malicioso-para-rce)
  - [Obtendo uma Reverse Shell](#obtendo-uma-reverse-shell)
- [Fase 4: Capturando a Flag](#-fase-4-capturando-a-flag)
  - [Lendo o Arquivo `wp-config.php`](#lendo-o-arquivo-wp-configphp)
  - [Encontrando a Senha do Banco de Dados](#encontrando-a-senha-do-banco-de-dados)
- [Conclusão e Recomendações](#-conclusão-e-recomendações)
