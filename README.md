# Arquitetura do Sistema

```mermaid
graph TD;
    ERP[ERP - Sistema de Gestão] -->|Envia ordens de produção| MES[MES - Execução da Produção]
    MES -->|Envia status de produção| ERP
    MES -->|Coordena e monitora| SCADA[SCADA - Supervisão e Controle]
    SCADA -->|Supervisiona processos e alarmes| CLPs[CLPs - Controladores Lógicos Programáveis]
    CLPs -->|Recebem dados| Sensores[Sensores e Atuadores]
    Sensores -->|Enviam dados em tempo real| CLPs
    SCADA -->|Dados para visualização| Interface[Interface de Operação]
    ERP -->|Gerencia estoques e compras| Estoque[Gestão de Estoque]
    ERP -->|Planejamento e controle| PCP[Planejamento e Controle da Produção]
    ERP -->|Monitora qualidade| Qualidade[Controle de Qualidade]
    PCP -->|Planeja ordens de produção| MES
    Qualidade -->|Envia relatórios| ERP
