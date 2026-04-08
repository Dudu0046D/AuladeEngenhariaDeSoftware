flowchart TD
    start((Inicio)) --> receber[Receber Pedido]

    receber --> fork{Fork}

    %% Fluxo principal
    fork --> preencher[Preencher Pedido]

    %% Decisão
    preencher --> decisao{Tipo de Entrega}
    decisao -->|Rapida| entrega_rapida[Entrega Rapida]
    decisao -->|Normal| entrega_normal[Entrega Normal]

    %% União (merge)
    entrega_rapida --> uniao{Uniao}
    entrega_normal --> uniao

    %% Fluxo paralelo financeiro
    fork --> fatura[Enviar Fatura]
    fatura --> pagamento[Receber Pagamento]

    %% Junção final (join)
    uniao --> juncao{Juncao}
    pagamento --> juncao

    juncao --> fechar[Fechar Pedido]
    fechar --> fim((Fim))
