```mermaid
erDiagram
    PROFESSOR {
        int id PK
        string nome
        date data_nascimento
    }

    DISCIPLINA {
        int id PK
        string nome
        int professor_id FK
    }

    ALUNO {
        int id PK
        string nome
    }

    MATRICULA {
        int id PK
        int aluno_id FK
        int disciplina_id FK
        string semestre
        decimal nota
    }

    AVALIACAO_LOG {
        int id PK
        int aluno_id FK
        timestamp data_acesso
    }

    PROFESSOR ||--o{ DISCIPLINA : leciona
    ALUNO ||--o{ MATRICULA : realiza
    DISCIPLINA ||--o{ MATRICULA : possui
    ALUNO ||--o{ AVALIACAO_LOG : gera
