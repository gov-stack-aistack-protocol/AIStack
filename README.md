# AIStack
Protocolo distribuído de comunicação entre agentes de IA ultrarrápido,
semântico, eficiente e seguro


[![License](https://img.shields.io/badge/license-CC0,_Apache--2.0-
brightgreen.svg)](LICENSE.md)
[![CI
Lint](https://github.com/root/AIStack/actions/workflows/lint.yml/badge.svg)]
(https://github.com/root/AIStack/actions/workflows/lint.yml)
[![Discord](https://img.shields.io/badge/chat-Discord-blue?logo=discord)]
(https://discord.gg/aistack)
![GitHub contributors](https://img.shields.io/github/contributors/root/AIStack)


## Sobre o AIStack

AIStack é um protocolo de comunicação de próxima geração entre agentes de inteligência artificial, projetado para atuar como **HTTP/QUIC para IAs** - fornecendo uma pilha que une:

- Transporte QUIC+IA com **multiplexação inteligente e controle adaptativo**
- Formato binário leve `µProto` com **delta-encoding semântico**
- Sistema de descoberta via **OpenAPI v4 / agent-card.json**
- Handshake seguro com **DID descentralizado** e **criptografia pós-quântica FIPS 203 (CRYSTALS-Kyber)**
- Roteamento P2P semântico, compressão neural e QoS por contexto

> “Ei, seria ótimo se as IAs trocassem dados como humanos trocam mensagens: rápido,
> eficiente e confiável.”
> — Definição da visão do AIStack

---

## Por que isso importa?

Os sistemas atuais de comunicação entre IAs se baseiam em chamadas como HTTP/TCP, que funcionam razoavelmente, mas não foram desenhados para otimizar a
troca de grandes vetores de estado e inferências em tempo real. O AIStack resolve isso com:

- **Latência sub-µs** em clusters e malhas edge
- **Ganho de performance** e economia de banda (compressão IA + delta)
- **Confiabilidade e autenticidade** garantidas por identidade descentralizada
- **Escalabilidade colaborativa**, sem depender de servidores centralizados

---

## Recursos principais
- **Latência baixa** via QUIC e transporte RDMA
- **SemBatch** para agrupamento semântico de mensagens
- **Handshake DID-Kyber** para segurança pós-quântica
- **µProto** como esquema binário lean
- **Overlay P2P semântico** com anycast 
- **Telemetria atômica** para ajuste e observabilidade 

---

## Começando (Preview)

```bash
git clone https://github.com/ai-stack/AIStack.git
cd AIStack
# Visualizar o spec OpenAPI
less spec/discovery/v1/openapi.yaml
# Emular handshake em Go (fora do Linux)?
go run simulator/handshake_demo.go
