<!-- CONTRIBUTING.md for AIStack project -->

# 🤝 Como Contribuir com o AIStack

Obrigado por considerar contribuir com o AIStack — o protocolo de comunicação de alto desempenho entre agentes de IA. Seja você arquiteto, pesquisador, engenheiro de redes ou curador de documentação, sua participação é bem-vinda!

---

## 📖 Índice

1. [Antes de Começar](#antes-de-começar)  
2. [Escopo de Contribuições](#escopo-de-contribuições)  
3. [Como Relatar Issues ou Bugs](#como-relatar-issues-ou-bugs)  
4. [Como Enviar um Pull Request (PR)](#como-enviar-um-pull-request-pr)  
5. [Padrões de Estilo e Qualidade](#padrões-de-estilo-e-qualidade)  
6. [Processo de Revisão e Aceitação](#processo-de-revisão-e-aceitação)  
7. [Formas de Participação Não Técnica](#formas-de-participação-não-técnica)  
8. [Reconhecimento & Ascenção Comunitária](#reconhecimento--ascensão-comunitária)  
9. [Canais de Comunicação](#canais-de-comunicação)  
10. [Contactar um Revisor](#contactar-um-revisor)  
11. [Apêndices](#apêndices)

---

## Antes de Começar

- Leia o [README.md](./README.md) para entender a visão e arquitetura do AIStack.  
- Veja o [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md) para conhecer o nosso compromisso com um espaço respeitoso e inclusivo.  
- Instale ferramentas básicas:
  - Git (v2.34+), Go/Rust (dependendo do módulo), flatc ou Cap’n Proto, NS‑3 (optional).  
- Faça um "fork" do repositório oficial e clone para sua máquina local.

---

## Escopo de Contribuições

### 🧰 Exemplos de contribuições tipicamente aceitas:

- Correções ou melhorias de documentação (ex: design, spec, tutorials)  
- Templates OpenAPI / AsyncAPI ou exemplos de JSON para AgentCard / DiscoverRequest  
- Patches no simulador Go (`quic-go` fork) ou NS‑3 (fluxo semBatch, latências especificadas)  
- Scripts ou ferramentas CLI para handshake DID-Kyber ou geração de pares DID públicos/privados  
- Testes automatizados ou benchmarks de latência/throughput  

### 🐣 Primeiros passos recomendados:

- Busque issues com etiqueta **`good first issue`**  
- Comece por tarefas de documentação, exemplos básicos ou correções triviais para ambientar-se com o código ([Open Source Guides](https://opensource.guide/contributing/#what-are-contributions?utm_source=chatgpt.com)) :contentReference[oaicite:0]{index=0}  

---

## Como Relatar Issues ou Bugs

1. Verifique se o problema já existe. Se sim, comente na issue existente.
2. Use o template “bug report” pré-criado ou formate o título como:
