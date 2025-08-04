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
## Por que um protocolo de comunicação para IAs?

Imagine o tráfego em uma cidade: ruas estreitas, sem semáforos, onde todo mundo tenta passar ao mesmo tempo. Os veículos ficam parados, as buzinas tocam sem parar e ninguém chega ao destino a tempo. Agora pense em algo diferente: avenidas largas, semáforos sincronizados, sinalização clara e faixas exclusivas para emergências. O trânsito flui melhor, os ônibus passam na hora certa e o serviço de ambulância chega em poucos minutos.

Hoje, as inteligências artificiais (IAs) conversam entre si usando regras e caminhos semelhantes às ruas estreitas da cidade sem sinalização: cada chamada de API ou troca de dados passa por protocolos genéricos (como HTTP/TCP) que não foram pensados especificamente para o tipo de informação que IAs trocam. É eficiente o bastante para muitas tarefas, mas cria atrasos, gargalos de dados e altos custos de computação — exatamente como o congestionamento urbano.

O **Protocolo AIStack** (nome provisório) foi idealizado para ser essas avenidas largas, semaforização inteligente e faixa exclusiva: um canal de comunicação feito sob medida para as necessidades das IAs:

- **Velocidade**: troca de informações em microssegundos, permitindo reações quase instantâneas.
- **Eficiência**: comprime só o que é relevante, eliminando ruído e reduzindo até cem vezes o volume de dados trocados.
- **Confiabilidade** e Segurança: identidades digitais verificadas, criptografia resistente a ataques futuros e recuperação automática de falhas.
- **Escalabilidade**: não depende de um ponto central — cada IA se conecta às mais próximas em termos de contexto, como se seguisse o caminho mais rápido até o destino.
- **Observabilidade Inteligente**: todas as movimentações são monitoradas em tempo real para ajustar semáforos e faixas conforme a necessidade.


## Por que isso importa para qualquer pessoa?

- **Interações mais rápidas com assistentes virtuais**: ao fazer perguntas complexas, o tempo de resposta diminui, tornando a conversa muito mais fluida.
- **Serviços críticos mais seguros e precisos**: em emergências médicas ou financeiras, as decisões baseadas em IA chegam antes e com maior confiança.
- **Experiências imersivas**: jogos, realidade virtual e robótica responderão em frações de segundo, ampliando o limite do que é possível.
- **Redução de custos de infraestrutura**: processar menos dados e gastar menos energia é bom para empresas e para o meio ambiente.

Em resumo, o AIStack transforma como IAs dirigem no trânsito digital. Isso significa serviços mais rápidos, seguros e econômicos para todos — desde o usuário que conversa com um chatbot até a fábrica que coordena robôs em linha de produção.

## Por que isso importa de modo geral?

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
