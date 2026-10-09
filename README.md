# ShareBook


> Substitua os trechos entre colchetes `[ ]` pelas informações reais do trabalho. Remova esta nota e as demais orientações em *itálico* antes da entrega.


[![Status](https://img.shields.io/badge/status-[em_desenvolvimento]-yellow)]()
[![Versão](https://img.shields.io/badge/versão-[0.1.0]-blue)]()
[![Licença](https://img.shields.io/badge/licença-[acadêmica]-lightgrey)]()


**Instituição:** Centro Educacional Unificado de Brasília
**Curso:** Ciências da Computação  
**Disciplina:** Desenvolvimento Web  
**Turma / Semestre:** Turma B 4° Semestre  
**Professor(a):** Felippe Pires
**Status do projeto:** Em desenvolvimento


---


## Sumário


- [1. Descrição do projeto](#1-descrição-do-projeto)
- [2. Funcionalidades](#2-funcionalidades)
- [3. Demonstração](#3-demonstração)
- [4. Tecnologias utilizadas](#4-tecnologias-utilizadas)
- [5. Arquitetura](#5-arquitetura)
- [6. Organização dos diretórios](#6-organização-dos-diretórios)
- [7. Participantes](#7-participantes)
- [8. Como executar](#8-como-executar)
- [9. Configuração](#9-configuração)
- [10. Testes](#10-testes)
- [11. Uso de inteligência artificial](#11-uso-de-inteligência-artificial)
- [12. Contribuição e fluxo de trabalho](#12-contribuição-e-fluxo-de-trabalho)
- [13. Histórico de versões](#13-histórico-de-versões)
- [14. Limitações e próximos passos](#14-limitações-e-próximos-passos)
- [15. Licença, referências e contato](#15-licença-referências-e-contato)


---


## 1. Descrição do projeto


A ShareBook é uma plataforma criada para facilitar o compartilhamento de livros entre pessoas,a ideia é permitir que os usuários cadastrem os livros que possuem e possam disponibilizá-los para outras pessoas que tenham interesse em ler essas obras.


O objetivo da plataforma é tornar o acesso aos livros mais fácil e incentivar o hábito da leitura e assim, em vez de um livro ficar parado na estante, ele pode ser compartilhado com outra pessoa que queira lê-lo.


A ShareBook também busca organizar esse processo de forma simples, reunindo informações sobre os livros e seus usuários em um único lugar. Dessa forma, a plataforma facilita a busca e o compartilhamento de livros entre a comunidade.




### Objetivos


*Liste os objetivos gerais e específicos do projeto.*


- **Objetivo geral:** Facilitar o compartilhamento de livros e incentivar o interesse de ler
- **Objetivos específicos:**
- Permitir o cadastro e autenticação de usuários.
- Permitir que os usuários cadastrem e gerenciem seus livros.
- Facilitar a busca e consulta de livros disponíveis para compartilhamento.
- Permitir que os usuários solicitem o compartilhamento de livros.
- Registrar e gerenciar os empréstimos e devoluções dos livros.
- Manter organizado o histórico de livros compartilhados entre os usuários.




### Público-alvo


- Leitores
- Estudantes
- Colecionadores
---


## 2. Funcionalidades


| Funcionalidade | Descrição | Status |
| --- | --- | --- |
| [Filtragem de livros] | [Filtros designados aos livros para facilitar pesquisa.] | [Em andamento] |
| [Cadastro de livros] | [Cadastro de livros com título, autor, gênero e descrição] | [Em andamento] |
| [Solicitação de livros] | [Solicitação de livros disponíveis para compartilhamento ] | [planejada] |


### Requisitos não funcionais


- **Desempenho:** [respostas da API em menos de 3 segundos]
- **Segurança:** [senhas armazenadas com hash, HTTPS e tempo de inatividade pede uma nova autenticação]
- **Usabilidade:** [interface responsiva para desktop e celular]
- **Disponibilidade:** [O sistema deve estar disponível sempre que necessário para que os usuários possam consultar e gerenciar os livros cadastrados. ]


---


## 3. Demonstração


*Inclua capturas de tela, GIF ou link para vídeo. Coloque as imagens em `images/`.*


![Tela principal] (image.png)


| Tela | Descrição |
| --- | --- |
| [Login] | [Acesso ao sistema com e-mail e senha] |
| [Painel] | [Visão geral das reservas do dia] |


**Vídeo / protótipo:** [URL do YouTube, Loom ou Figma]


---


## 4. Tecnologias utilizadas


*Informe as tecnologias de fato usadas no projeto. Remova as linhas que não se aplicarem.*


| Camada | Tecnologia | Versão |
| --- | --- | --- |
| Linguagem | [Python] | [3.14.8] |
| Frontend | [HTML, CSS] | [5.1] |
| Backend | [Flask] | [3.1.3] |
| Banco de dados | [SQLite] | [3.53.4] |
| Testes | [pytest] | [9.1.1] |
| Infraestrutura | [Docker, GitHub Actions] | — |
| Outras ferramentas | [Git] | — |


---


## 5. Arquitetura

[A ShareBook é organizada em camadas que dividem as responsabilidades do sistema. A interface permite que os usuários façam login, cadastrem e pesquisem livros. A aplicação processa as ações, enquanto o banco de dados armazena as informações dos usuários, livros e empréstimos.

O funcionamento é simples: o usuário realiza uma ação na interface, o sistema processa a solicitação e consulta ou salva os dados no banco de dados. Por fim, o resultado é exibido ao usuário.]


```text
[Usuário]
    ↓
[Interface / Frontend]
    ↓
[Aplicação / Regras de negócio]
    ↓
[Banco de dados / Persistência]
    ↓
[Retorno das informações ao usuário]
```


**Decisões relevantes:**


- [Uso de uma arquitetura em camadas para separar a interface, a lógica de negócio e o banco de dados.]
- [Armazenamento relacional para organizar os dados de usuários, livros e empréstimos, que possuem relacionamentos entre si.]


### Endpoints principais (quando houver API)


| Método | Rota | Descrição |
| --- | --- | --- |
| `POST` | `/api/[usuarios]` | [Cadastrar um usuário] |
| `POST` | `/api/[login]` | [Realizar login] |
| `GET` | `/api/[livros]` | [listar livros disponíveis] |
| `POST` | `/api/[livros]` | [Cadastrar um livro] |
| `PUT` | `/api/[livros]/{id}` | [Atualizar informações de um livro] |
| `DELETE` | `/api/[livros]/{id}` | [Remover um livro] |

Documentação completa da API: [link para Swagger, Postman ou `docs/api.md`]


---


## 6. Organização dos diretórios


*Mantenha a árvore alinhada à estrutura real do repositório. Ajuste pastas conforme o tipo de projeto.*


```text
.
├── README.md                               # Documentação principal do projeto
├── image.png                               # Captura de tela geral/demonstração
├── docs/                                   # Artefatos técnicos e modelagem do projeto
│   ├── ShareBook - Documento de Visão.pdf  # Documento de visão do projeto
│   └── modelagem/                          # Modelos e diagramas UML/ER
│       ├── banco-de-dados/                 # Modelagem do banco de dados
│       │   └── DiagramER.pdf               # Diagrama Entidade-Relacionamento
│       ├── casos-de-uso/                   # Diagramas de interações e atores
│       │   └── Diagrama de caso de uso - ShareBook.png
│       └── classes/                        # Diagrama de classes UML
│           └── DiagramClasse.png
├── images/                                 # Imagens auxiliares da documentação
│   └── semaforo.png                    # Imagem da política de uso de IA
└── venv/                               # Ambiente virtual do Python (não versionado)
```


| Diretório / arquivo | Função |
| --- | --- |
| `README.md` | Apresentação do projeto, objetivos, tecnologias e instruções de uso |
| `image.png` | Imagem de apresentação/demonstração exibida no README |
| `docs/` | Artefatos de análise, modelagem e documento de visão do projeto |
| `docs/modelagem/` | Diagramas de casos de uso, classes e ER |
| `images/` | Figuras da documentação geral |
| `venv/` | Ambiente virtual com as dependências do Python instaladas |

---


## 7. Participantes


*Informe nome completo, função no grupo e, se houver, o identificador acadêmico (matrícula).*


| Nome | Matrícula | Função no projeto |
| --- | --- | --- |
| [Leonardo Soares Paes] | [22505652] | [Ex.: coordenação / backend / frontend / testes / documentação] |
| [Arthur Sant' Anna da Silveira] | [22501763] | [Ex.: coordenação / backend / frontend / testes / documentação] |

**Professor(a) responsável:** [Felippe Pires]


---


## 8. Como executar


*Preencha com os comandos reais do projeto para que outra pessoa consiga reproduzir o ambiente.*


### Pré-requisitos


- [Git]
- [Python 3.12+]
- [Django]
- [node.js]

### Instalação e execução


```bash
# 1. Clonar o repositório
git clone [https://github.com/Arthur-Sant-Anna/ShareBook.git]


# 2. Instalar dependências
[cd ShareBook]


# 3. Configurar variáveis de ambiente
cp .env.example .env
# edite o arquivo .env com as credenciais locais


# 4. Executar a aplicação
[comando de execução]
```


**Acesso local:** [Ex.: http://localhost:3000]


### Implantação (quando houver)


- **Ambiente:** [Ex.: Render, Railway, Vercel, servidor da instituição]
- **URL de produção:** [https://...]
- **Observações:** [Ex.: é necessário configurar as variáveis de ambiente no painel do provedor]


---


## 9. Configuração


*Liste as variáveis de ambiente usadas pelo sistema. Nunca publique senhas, tokens ou chaves neste arquivo.*


| Variável | Obrigatória | Descrição | Exemplo |
| --- | --- | --- | --- |
| `PORT` | Sim | Porta da aplicação | `3000` |
| `DATABASE_URL` | Sim | Conexão com o banco | `postgresql://user:senha@localhost:5432/app` |
| `SECRET_KEY` | Sim | Chave de sessão / JWT | `[gerar localmente]` |


Credenciais reais devem ficar apenas no arquivo `.env` (não versionado).


---


## 10. Testes


*Descreva como executar os testes e o que eles cobrem.*


```bash
[comando para executar os testes]
```


| Tipo | Ferramenta | O que verifica |
| --- | --- | --- |
| Unitários | [Ex.: pytest / JUnit / Jest] | [Ex.: regras de negócio isoladas] |
| Integração | [Ex.: ...] | [Ex.: API e banco de dados] |
| Manuais | [Ex.: checklist em `docs/`] | [Ex.: fluxos principais da interface] |


**Cobertura atual:** [Ex.: 70% / não medida]


---


## 11. Uso de inteligência artificial


Este repositório segue a política de uso de IA da disciplina (semáforo pedagógico):


![Política de uso de IA — semáforo](images/semaforo.png)


| Situação | Significado |
| --- | --- |
| **Vermelho — uso proibido** | Atividades de autonomia intelectual (ex.: provas presenciais sem consulta). |
| **Amarelo — uso limitado** | IA pode ser ferramenta auxiliar, desde que haja declaração de uso. |
| **Verde — uso permitido** | Uso livre ao longo da atividade acadêmica. |


### Declaração de uso


*Preencha de forma honesta. Se não houve uso de IA, declare explicitamente.*


- **Houve uso de IA neste projeto?** [Sim]
- **Ferramentas utilizadas:** [ChatGPT/Gemini]
- **Finalidade:** [geração de bases para inspiração, esclarecimento de dúvidas de sintaxe]
- **O que NÃO foi delegado à IA:** [definição do problema, modelagem, implementação das regras de negócio, testes finais, idealização de projetos]


---


## 12. Contribuição e fluxo de trabalho


*Padronize o trabalho em equipe. Ajuste as regras ao combinado da disciplina.*


### Branches


- `main` — versão estável para avaliação
- `develop` — integração do grupo *(opcional)*
- `feat/[nome]` — nova funcionalidade
- `fix/[nome]` — correção de defeito
- `docs/[nome]` — alterações só de documentação


### Commits


Use mensagens curtas e no imperativo, por exemplo:


- `feat: adiciona cadastro de reservas`
- `fix: corrige validação de data`
- `docs: atualiza instruções de execução`


### Passos sugeridos


1. Criar uma branch a partir de `main`.
2. Implementar e testar localmente.
3. Abrir um *pull request* / *merge request* para revisão do grupo.
4. Só então integrar à branch principal.


**Issues e quadro de tarefas:** [link do GitHub Projects, Trello ou similar]


---


## 13. Histórico de versões


*Registre entregas relevantes (sprints, checkpoints ou versões avaliadas).*


| Versão | Data | Descrição |
| --- | --- | --- |
| `0.0.1` | [2026-08-15] | [primeira versão] |

---


## 14. Limitações e próximos passos


### Problemas conhecidos


- [Ex.: atualização manual do banco de dados]


### Roadmap


- [ ] [Implementação do cadastro e login de usuário]
- [ ] [Desenvolvimento das funcionalidades de cadastro, edição, exclusão e busca de livros]
- [ ] [Implementação das solicitações de empréstimo e do controle de devoluções]
- [ ] [implantação da plataforma para disponibilização aos usuários.]
- [ ] [Melhorias na segurança e na experiência dos usuários.]


---


## 15. Licença, referências e contato


**Licença:** [uso acadêmico]


Este material destina-se a fins educacionais. Verifique com a disciplina se o código pode ser reutilizado fora do curso.


### Documentação complementar


- Índice da pasta `docs/`: [`docs/README.pdf`](docs/README.pdf)
- Casos de uso (diagrama + especificações): [`docs/modelagem/casos-de-uso/especificacoes-casos-de-uso.pdf`](docs/modelagem/casos-de-uso/especificacoes-casos-de-uso.pdf)
- Diagrama de classes: [`docs/modelagem/classes/diagrama-de-classes.pdf`](docs/modelagem/classes/diagrama-de-classes.pdf)
- Modelo conceitual (ER): [`docs/modelagem/banco-de-dados/diagrama-er.pdf`](docs/modelagem/banco-de-dados/diagrama-er.pdf)
- Modelo lógico: [`docs/modelagem/banco-de-dados/modelo-logico.pdf`](docs/modelagem/banco-de-dados/modelo-logico.pdf)
- Apresentação: [`docs/apresentacao.pdf`](docs/)


### Referências


- [Template do professor]


### Contato


Dúvidas sobre o projeto: [leonardo.sp@sempreceub.com e arthur.silveira@sempreceub.com]


**Agradecimentos:** [Felippe Pires]






