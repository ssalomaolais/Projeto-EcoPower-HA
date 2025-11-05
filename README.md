# Projeto EcoPower-HA: Gestão Inteligente e Preditiva de Energia Residencial 

**Gestão Inteligente e Preditiva de Energia Residencial com Goodwe e Home Assistant**

Este repositório contém todos os arquivos de configuração, documentação e scripts para o Projeto EcoPower-HA, uma solução integrada para a gestão inteligente de energia residencial. O projeto combina hardware de ponta da Goodwe com a plataforma open-source Home Assistant para criar um ecossistema energético otimizado, preditivo e resiliente


## 🎯 Sobre o Projeto

Este projeto responde ao desafio de criar uma solução energética que transcende o monitoramento padrão. Integramos inversores e baterias Goodwe com o Home Assistant para otimizar o autoconsumo, a eficiência energética e introduzir uma camada de inteligência preditiva usando machine learning (ML) e automações avançadas de *Demand-Side Management* (DSM).

## ✨ Diferenciais Inovadores 

* **Inteligência Preditiva (ML):** Utilizamos o add-on EMHASS  para passar de um controle reativo para um proativo. O sistema prevê a geração solar (com base no clima)  e o consumo residencial (com base em dados históricos)  para otimizar o uso da bateria.
* **Controle Local e Privacidade (Home Assistant):** Ao usar o Home Assistant como cérebro local, garantimos que o sistema funcione mesmo sem internet. Todos os dados críticos de consumo permanecem na rede local, assegurando privacidade e segurança.
* **Gestão Holística da Energia:** A plataforma integra-se com milhares de dispositivos (Zigbee, etc.), permitindo que o sistema gerencie não apenas a geração/bateria, mas também cargas da casa (como VEs e HVAC) para uma otimização completa.
* **UX Centrada no Usuário:** Dashboards intuitivos  e controle total por assistentes de voz (Google Assistant, Alexa) tornam a gestão de energia acessível para todos os moradores.

## 🏗️ Arquitetura da Solução

### Hardware Chave

| Componente | Modelo | Relevância para o Projeto |
| :--- | :--- | :--- |
| **Inversor Híbrido** | Goodwe GW6000-ES-G2 | Coração do sistema. empo de comutação < 10ms (nível UPS) permite resiliência ativa. |
| **Bateria** | Goodwe Lynx Home U | Tecnologia LFP segura e de longa vida. Modular (5.4 kWh) para *peak shaving* e consumo noturno. |
| **Smart Meter** | Goodwe (Monofásico) | Essencial. Fornece dados precisos de importação/exportação para os algoritmos de otimização. |
| **Servidor Local** | Mini-PC (Intel N95) | Executa o Home Assistant OS, EMHASS e InfluxDB 24/7 com baixo consumo de energia (~10-15W) |

### Software e Protocolos 

* **Plataforma:** Home Assistant 
* **Otimização (ML):** EMHASS 
* **Banco de Dados:** InfluxDB (para dados históricos de ML)
* **Configuração:** YAML 
* **Protocolos:** Zigbee (Sensores/Plugs), UDP/TCP (Comunicação com Inversor Goodwe) 

## 🛠️ Estrutura do Repositório 

* `/config/`: Arquivos de configuração do Home Assistant (`configuration.yaml`, `automations.yaml`, etc.).
* `/docs/`: Documentação detalhada, diagramas de arquitetura e guias.
* `/emhass/`: Arquivos de configuração específicos do add-on EMHASS.
* `/scripts/`: Scripts auxiliares para análise ou manutenção.
* `README.md`: Este arquivo.

## 🚀 Como Começar (Guia Rápido)

1.  **Hardware:** Instale o Inversor Goodwe, a Bateria Lynx e o Smart Meter conforme o manual do fabricante.
2.  **Servidor:** Instale o Home Assistant OS no Mini-PC.
3.  **Integração:** Adicione a integração nativa do Home Assistant para a Goodwe.
4.  **Configuração:** Copie os arquivos deste repositório para sua pasta `/config` do Home Assistant.
5.  **Otimização:** Instale e configure os add-ons EMHASS  e InfluxDB  (veja a pasta `/emhass/` e `/docs/`).
6.  **Dashboard:** Configure seu dashboard de energia (Lovelace).

## 🔒 Segurança

Este projeto implementa as melhores práticas de segurança, incluindo acesso remoto via Home Assistant Cloud (Nabu Casa), Autenticação de Múltiplos Fatores (MFA) e segmentação de rede (VLAN) para dispositivos IoT.

## 📈 Trabalhos Futuros

A arquitetura deste projeto é a base para a integração em uma **Usina de Energia Virtual (Virtual Power Plant - VPP)**. O controle local via API permite que o sistema preste serviços de rede (como estabilização de frequência) mediante solicitação de um agregador, transformando a residência em um participante ativo do mercado de energia.
