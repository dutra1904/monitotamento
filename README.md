```mermaid
graph LR
    classDef root fill:#2c3e50,stroke:#1a252f,stroke-width:3px,color:#ffffff,font-weight:bold;
    classDef branch fill:#34495e,stroke:#2c3e50,stroke-width:2px,color:#ffffff,font-weight:bold;
    classDef sub fill:#ecf0f1,stroke:#bdc3c7,stroke-width:2px,color:#2c3e50,font-weight:bold;
    classDef leaf fill:#ffffff,stroke:#95a5a6,stroke-width:1px,color:#34495e;

    Root["Sistema Inteligente Distribuído de Monitoramento de Ambientes (Lab. Química UFG)"]:::root

    %% ================= 1. ESCOPO =================
    Root --> E["ESCOPO"]:::branch
    
    E --> E1["SS1: Edge Computing e Sensoriamento"]:::sub
    E1 --> E1_1["ESP32 NodeMCU (Dual-Core)"]:::leaf
    E1 --> E1_2["Sensor de Gás MQ-135 (CO2/VOC)"]:::leaf
    E1 --> E1_3["Sensor Ambiental BME280 (I2C)"]:::leaf
    E1 --> E1_4["Sensor de Presença PIR (Digital)"]:::leaf
    E1 --> E1_5["Circuitos de Proteção"]:::leaf
    E1_5 --> E1_5a["Diodo Zener 3.6V (Proteção ADC)"]:::leaf
    E1_5 --> E1_5b["Divisor de Tensão (68k/33k Ohms)"]:::leaf
    E1_5 --> E1_5c["Capacitor 100nF (Desacoplamento)"]:::leaf

    E --> E2["SS2: Comunicação e Redes IoT"]:::sub
    E2 --> E2_1["Broker MQTT (Eclipse Mosquitto)"]:::leaf
    E2 --> E2_2["Qualidade de Serviço (QoS 1)"]:::leaf
    E2 --> E2_3["Last Will and Testament (LWT)"]:::leaf
    E2 --> E2_4["Mecanismo Keep-Alive (10s)"]:::leaf
    E2 --> E2_5["Payloads Estruturados (JSON)"]:::leaf

    E --> E3["SS3: Plataforma e Inteligência"]:::sub
    E3 --> E3_1["Java 17 + Spring Boot 3"]:::leaf
    E3 --> E3_2["InfluxDB (Séries Temporais)"]:::leaf
    E3 --> E3_3["Grafana (Dashboards em Tempo Real)"]:::leaf
    E3 --> E3_4["Algoritmos de Decisão"]:::leaf
    E3_4 --> E3_4a["Classificação de Risco Crítico"]:::leaf
    E3_4 --> E3_4b["Detecção de Vazamento Ambiental"]:::leaf
    E3_4 --> E3_4c["Auditoria de Uso Irregular"]:::leaf

    %% ================= 2. TAREFAS =================
    Root --> T["TAREFAS"]:::branch
    
    T --> T1["Conceber"]:::sub
    T1 --> T1_1["Levantamento de Requisitos de Segurança"]:::leaf
    T1 --> T1_2["Modelagem Lógica da Sub-rede"]:::leaf
    T1 --> T1_3["Especificação Técnica de Hardware"]:::leaf

    T --> T2["Preparar"]:::sub
    T2 --> T2_1["Aquisição e Homologação de Hardware"]:::leaf
    T2 --> T2_2["Burn-in de Sensores (24h Estabilização)"]:::leaf
    T2 --> T2_3["Modificação R_L (1k para 20k Ohms)"]:::leaf
    T2 --> T2_4["Configuração de Ambiente (Docker)"]:::leaf

    T --> T3["Executar"]:::sub
    T3 --> T3_1["Desenvolvimento SS1"]:::leaf
    T3_1 --> T3_1a["Kernel FreeRTOS (Prioridades)"]:::leaf
    T3_1 --> T3_1b["Filtro Digital EMA (Alpha 0.15)"]:::leaf
    T3_1 --> T3_1c["Calibração Dinâmica (R0)"]:::leaf
    T3 --> T3_2["Codificação Backend (Spring Boot)"]:::leaf
    T3 --> T3_3["Integração MQTT-InfluxDB (Upsert)"]:::leaf

    T --> T4["Finalizar"]:::sub
    T4 --> T4_1["Ensaios de Injeção de Gases"]:::leaf
    T4 --> T4_2["Validação de Alertas e LWT"]:::leaf
    T4 --> T4_3["Homologação Física e Defesa"]:::leaf

    %% ================= 3. RECURSOS E EQUIPE =================
    Root --> R["RECURSOS E EQUIPE"]:::branch
    
    R --> R1["Competências Necessárias"]:::sub
    R1 --> R1_1["Sistemas Embarcados e FreeRTOS"]:::leaf
    R1 --> R1_2["Arquitetura IoT e Protocolo MQTT"]:::leaf
    R1 --> R1_3["Desenvolvimento Java Corporativo"]:::leaf
    R1 --> R1_4["Eletrônica Analógica e Proteção"]:::leaf

    R --> R2["Composição Sugerida"]:::sub
    R2 --> R2_1["Analista de Sistemas / Backend"]:::leaf
    R2 --> R2_2["Engenheiro de Computação (Edge)"]:::leaf
    R2 --> R2_3["Técnico em Eletrotécnica"]:::leaf
    R2 --> R2_4["Estagiários (Eng. Elétrica/Comp)"]:::leaf

    %% ================= 4. METAS E RISCOS =================
    Root --> M["METAS E RISCOS"]:::branch
    
    M --> M1["Metas de Projeto"]:::sub
    M1 --> M1_1["Disparo de Alerta (PPM > 1200)"]:::leaf
    M1 --> M1_2["Resposta do Sistema (< 10ms)"]:::leaf
    M1 --> M1_3["Idempotência na Persistência"]:::leaf
    M1 --> M1_4["Monitoramento 24/7 sem Falsos Positivos"]:::leaf

    M --> M2["Riscos e Mitigações"]:::sub
    M2 --> M2_1["Brownouts (Fontes Independentes)"]:::leaf
    M2 --> M2_2["Ruído Analógico (Malha Blindada)"]:::leaf
    M2 --> M2_3["Perda de Nó (Alerta de Testamento)"]:::leaf
    M2 --> M2_4["Saturação de Gás (Calibração Ativa)"]:::leaf
    M2 --> M2_5["Fadiga Térmica (Alimentação 5V/2A)"]:::leaf

    %% ================= 5. MELHORIAS FUTURAS =================
    Root --> F["MELHORIAS FUTURAS"]:::branch
    
    F --> F1["Recarga Solar (Células Fotovoltaicas)"]:::leaf
    F --> F2["Visão Computacional / Câmera Térmica"]:::leaf
    F --> F3["Processamento de Dados na Borda (Edge AI)"]:::leaf
