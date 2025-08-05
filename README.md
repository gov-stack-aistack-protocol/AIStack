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

## COMO PROJETAR UM PROTOCOLO DE COMUNICAÇÃO COMO O AIStack?

Para projetar um protocolo de comunicação entre IAs que seja simultaneamente ultra-rápido, eficiente, econômico e extremamente eficaz, precisamos repensar camadas, formatos e mecanismos já consolidados e introduzir inovações alinhadas aos gargalos atuais. A seguir, um esboço de especificação de alto nível, organizado em blocos:

---

## 1. Camada Física e de Enlace

* **Transporte Óptico Direto**

  * Uso de interconexões fotônicas em backplanes dedicados, minimizando conversões elétricas e latência (\~nanosegundos).
* **RDMA sobre Fabric Inteligente**

  * Memória remota direta (RDMA) com switches “smartNICs” que possam aplicar filtragem e roteamento de pacotes já na camada de enlace.

### 2. Transporte e Controle de Fluxo

* **QUIC+IA**

  * Baseado em QUIC para conexão sem “head-of-line blocking”, mas com aceleração adaptativa pelo próprio agente de IA monitorando condições (congestionamento, atraso).
* **Agrupamento Semântico de Pacotes (Semantic Batching)**

  * Em vez de agrupar por bytes, agrupa mensagens por contexto semântico (p.ex. solicitações que afetam o mesmo modelo ou tópico), reduzindo overhead de handshake e ACK.

### 3. Formato de Mensagem e Serialização

* **IDL Binário Lean (µProto)**

  * Um “micro-Protobuf” / FlatBuffers otimizado:

    * Tipos básicos (float16, int8/16/32)
    * Campos opcionais omitidos completamente
    * Delta-encoding de tensores (envia apenas diferenças em relação ao estado anterior)
* **Compressão Aprendida “On-The-Fly”**

  * Modelos de compressor/descompressor treinados para o tipo de dado (embeddings, gradientes, metadados), alcançando taxas maiores que gzip/zstd.

### 4. Descoberta e Roteamento

* **Overlay P2P Inteligente**

  * Cada nó mantém um mapeamento vetorial de afinidade de modelos/serviços, usando grafos esparsos de proximidade (p.ex. HNSW) para rotear mensagens pela “topologia semântica” mais curta.
* **Canal “Anycast Semântico”**

  * Uma mesma mensagem pode ser entregue ao nó mais próximo que tenha o contexto ou modelo desejado, reduzindo hops.

### 5. Segurança e Identidade

* **DIDs e Criptografia Pós-Quântica**

  * Identificadores descentralizados (DID) para cada agente; criptografia baseada em esquemas resistentes a computadores quânticos (p.ex. CRYSTALS-KYBER).
* **Trustless Handshake**

  * Troca de chaves efêmeras com verificação baseada em blockchain de consórcio, sem necessidade de autoridades centrais.

### 6. Qualidade de Serviço (QoS) e Prioritização

* **Tags de Latência Crítica**

  * Tráfego de inferência em tempo real (p.ex. streaming de decisões em milissegundos) marcado com prioridade máxima.
* **Controle Dinâmico de Lotes**

  * Ajuste automático do tamanho de lote e taxa de envio conforme métricas de fila do receptor e uso de GPU/TPU.

### 7. Resiliência e Consistência

* **Isolamento por CRDTs**

  * Estados compartilhados (p.ex. parâmetros de modelo distribuído) mantidos via CRDTs, proporcionando convergência eventual sem locking.
* **Fallback de Conteúdo Parcial**

  * Se um nó cair, outros agentes podem extrapolar a última versão recebida usando modelos de previsão de gradiente, evitando stalls.

### 8. Observabilidade e Telemetria

* **Canal Out-Of-Band de Metadados**

  * Métricas (latência, perda, throughput, uso de GPU) enviadas por fluxo separado, permitindo ajustes pró-ativos.
* **Tracing Semântico**

  * Cada mensagem carrega um “semtraceID” que resume o caminho semântico percorrido, facilitando debugging de fluxo de dados de alto nível.

---

#### Fluxo Típico de Uma Requisição de Inferência

1. **Descoberta**: IA remetente consulta overlay semântico para encontrar o nó “mais próximo” que execute o modelo X.
2. **Handshake**: Troca rápida de chaves curtíssimas (DID + pós-quântico) em 1–2 RTTs de QUIC+.
3. **Envio de Dados**:

   * Serialização via µProto e delta-encoding.
   * Compressão por modelo e empacotamento semântico.
4. **Processamento**:

   * O “smartNIC” já identifica prioridade e carrega diretamente na GPU do receptor via RDMA.
5. **Resposta**:

   * Lote de resultados é enviado de volta com QoS elevadíssima.
6. **Telemetria**:

   * Em paralelo, nodo receptor envia métricas de performance que alimentam o próximo ajuste adaptativo de janela de congestionamento.

---

## Por que esse protocolo seria “o melhor”?

* **Latência Sub-milissegundo**: Fotônica + RDMA + QUIC+AI
* **Alta Eficiência de Banda**: Delta-encoding + compressão inteligente
* **Econômico em Recursos**: SmartNICs e bypass de CPU minimizam gastos de energia
* **Escalabilidade**: Overlay P2P sem gargalos de “super-nó” central
* **Segurança Robusta**: DIDs + criptografia pós-quântica
* **Resiliência Nativa**: CRDTs e fallback preditivo evitam downtime
* **Observabilidade Ativa**: Telemetria sem atrapalhar o canal de dados

Com esses elementos integrados, você teria um protocolo de comunicação entre IAs verdadeiramente de próxima geração, capaz de atender às demandas de latência, eficiência e custo que projetamos.




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
