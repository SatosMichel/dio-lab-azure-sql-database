# Laboratório DIO: Processo Teórico de Criação de um Banco de Dados SQL na Azure

Este repositório documenta o processo teórico para a criação de um Banco de Dados SQL na Microsoft Azure. O projeto foi desenvolvido como parte de um desafio da plataforma DIO, com o objetivo de estudar e detalhar as etapas de configuração de um serviço de PaaS (Plataforma como Serviço) na nuvem.

## 🎯 Objetivo

O objetivo deste laboratório foi estudar e documentar de forma clara e estruturada o fluxo de provisionamento de um Banco de Dados SQL no Azure. O foco está na compreensão dos conceitos-chave, como a configuração de servidores lógicos, regras de firewall e níveis de serviço, servindo como um guia de referência para futuras implementações práticas.

## 🛠️ Conceitos-Chave Envolvidos

* **Azure SQL Database:** Serviço de banco de dados relacional totalmente gerenciado (PaaS), onde a Azure cuida de toda a infraestrutura, atualizações e backups.
* **Servidor Lógico SQL:** Atua como um ponto de administração central para um ou mais bancos de dados. Ele gerencia logins, regras de firewall e configurações de desempenho.
* **Regras de Firewall:** A principal camada de segurança que controla quais endereços IP têm permissão para se conectar ao servidor de banco de dados.
* **Nível de Serviço (DTU/vCore):** Modelo de computação e armazenamento que define o desempenho e o custo do banco de dados. A escolha de um nível adequado (ex: Básico, Standard) é crucial para o gerenciamento de custos.

## 🚀 Passo a Passo Detalhado (Processo Teórico)

A seguir, são descritas as etapas sequenciais para criar um Banco de Dados SQL no portal do Azure.

---

### **1. Acesso ao Serviço**

* **Ação:** No portal do Azure, a primeira ação é utilizar a barra de busca principal para encontrar o serviço **"Banco de Dados SQL do Azure"**.
* **Resultado:** Clicar no serviço para ser direcionado à sua página de gerenciamento.

---

### **2. Início da Criação**

* **Ação:** Na página do serviço, clicar no botão **"+ Criar"** para iniciar o assistente de configuração.

---

### **3. Configuração do Servidor Lógico**

* **Contexto:** Um banco de dados SQL precisa residir dentro de um "servidor lógico". Como este é o primeiro, um novo servidor precisa ser criado.
* **Ações:**
    * Clicar em **"Criar novo"** no campo "Servidor".
    * Preencher o formulário com um **nome de servidor globalmente único** (ex: `servidor-sql-dio-seu-nome`).
    * Definir a **Localização** como `(South America) Brazil South` para menor latência.
    * Escolher **"Usar autenticação do SQL"** como método de autenticação.
    * Criar um **logon de administrador** e uma **senha forte**, que devem ser armazenados em local seguro.

---

### **4. Configuração do Banco de Dados**

* **Ações:**
    * Definir um **Nome do banco de dados** (ex: `dioprojectdb`).
    * Clicar em **"Configurar banco de dados"** para escolher o nível de serviço.
    * **Ponto Crítico (Custo):** Selecionar uma camada de baixo custo, como **Básico** ou **Standard S0**, que é ideal para ambientes de estudo e desenvolvimento.

---

### **5. Configuração de Rede e Firewall**

* **Contexto:** Esta é a etapa mais importante para garantir a segurança e o acesso ao banco de dados.
* **Ações:**
    * Navegar até a aba **"Rede"**.
    * Marcar **"Sim"** na opção "Permitir que serviços e recursos do Azure acessem este servidor".
    * Clicar no botão **"+ Adicionar endereço IPv4 do cliente atual"**. Esta ação adiciona o IP da sua rede à lista de permissões, permitindo que você se conecte a partir de sua máquina.

---

### **6. Revisão e Implantação**

* **Ação:** Clicar no botão **"Revisar + criar"**. O Azure fará uma validação final de todas as configurações.
* **Resultado:** Se a validação for aprovada, o botão **"Criar"** ficará disponível para iniciar o provisionamento dos recursos.

---

### **7. Acesso Pós-Criação**

* **Ação:** Após a conclusão da implantação, navegar até a página do recurso criado.
* **Informação Chave:** Na tela de "Visão geral", o **"Nome do servidor"** estará visível. Este é o endereço que seria usado em uma ferramenta de gerenciamento de banco de dados (como SSMS ou DBeaver) para estabelecer a conexão.

---

## 📝 Nota Sobre as Capturas de Tela

Para otimizar os custos associados aos recursos da nuvem e garantir a utilização consciente da assinatura do Azure, optei por realizar este laboratório de forma teórica. As etapas descritas acima representam o fluxo exato do processo de criação, porém as capturas de tela foram omitidas deliberadamente para evitar o provisionamento e a eventual cobrança dos serviços.

## ✅ Conclusão

O estudo teórico do processo de criação de um Banco de Dados SQL no Azure evidencia a eficiência do modelo PaaS. Toda a complexidade de infraestrutura é abstraída, permitindo que o foco seja direcionado para a configuração do serviço, a segurança de acesso via firewall e a gestão de custos através da escolha do nível de serviço. Este exercício reforça o conhecimento necessário para provisionar bancos de dados relacionais na nuvem de forma segura e econômica.
