classDiagram
    %% Hierarquia de Usuários
    class Usuario {
        <<Abstract>>
        +String nome
        +String cpf
        +String email
    }

    class Aluno {
        +String matricula
    }

    class Professor {
        +String titulacao
    }

    class Organizador {
        +registrarPresenca(inscricao: Inscricao)
    }

    %% Entidades Principais
    class Evento {
        +String titulo
        +Date data
        +int cargaHoraria
        +int limiteVagas
    }

    class Palestrante {
        +String nome
        +String miniCurriculo
    }

    %% Classe de Associação / Relacional
    class Inscricao {
        +Date dataInscricao
        +StatusInscricao status
        +boolean presencaConfirmada
        +gerarCertificado()
    }

    class StatusInscricao {
        <<enumeration>>
        PENDENTE
        CONFIRMADA
    }

    %% Relacionamentos
    Usuario <|-- Aluno : é um
    Usuario <|-- Professor : é um
    Usuario <|-- Organizador : é um

    Usuario "1" -- "0..*" Inscricao : realiza
    Evento "1" -- "0..*" Inscricao : recebe
    Evento "*" -- "1..*" Palestrante : possui
    Inscricao .. StatusInscricao : usa
