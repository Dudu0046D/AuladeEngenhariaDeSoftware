mermaid
flowchart TD
    A([Início]) --> B[Receber Pedido]

    B --> C{Processos paralelos}

    C --> D[Preencher Pedido]
    D --> E[Realizar Entrega]

    C --> F[Enviar Fatura]
    F --> G[Receber Pagamento]

    E --> H{Join}
    G --> H

    H --> I[Fechar Pedido]
    I --> J([Fim])
