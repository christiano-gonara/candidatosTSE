# Candidatos TSE

Aplicação web para consultar candidaturas de Minas Gerais a partir do arquivo de dados eleitorais incluído no projeto. É possível pesquisar candidatos por nome, nome de urna ou número e combinar a busca com filtros de cargo e partido.

> Projeto acadêmico desenvolvido como atividade avaliativa. As informações exibidas vêm do arquivo de dados incluído no repositório e podem não refletir atualizações posteriores.

## Funcionalidades

- Busca textual por nome civil, nome de urna ou número do candidato.
- Filtros por cargo e partido, com opções carregadas a partir dos dados.
- Exibição de nome de urna, número, cargo, partido e, quando disponíveis, situação da candidatura, idade, ocupação e escolaridade.
- Leitura do CSV na inicialização da aplicação e filtragem em memória.
- Interface responsiva para desktop e dispositivos móveis.

## Tecnologias

- Java 25
- Spring Boot 4.1.1
- Spring MVC e Thymeleaf
- OpenCSV
- HTML e CSS
- Maven Wrapper

## Requisitos

- JDK 25
- Git (opcional, para clonar o projeto)

## Executar localmente

Clone o repositório e entre na pasta do projeto Maven:

```bash
git clone https://github.com/christiano-gonara/candidatosTSE.git
cd candidatosTSE/CandidatosTSE
```

Inicie a aplicação:

```bash
./mvnw spring-boot:run
```

No Windows, use:

```powershell
.\mvnw.cmd spring-boot:run
```

Depois, abra [http://localhost:8080](http://localhost:8080) no navegador.

## Testes

Na pasta `CandidatosTSE`, execute:

```bash
./mvnw test
```

## Dados

O arquivo usado pela aplicação está em `CandidatosTSE/src/main/resources/data/candidatos/consulta_cand_2026_MG.csv`. O serviço lê o CSV com separador `;` e codificação ISO-8859-1, mapeia os campos usados na interface e mantém os registros em memória durante a execução.

O conjunto de dados contém informações pessoais e eleitorais de candidatos. Use os dados apenas para consulta informativa, respeitando as condições de uso da fonte e a legislação aplicável. A aplicação não deve ser interpretada como recomendação ou endosso a qualquer candidatura.

## Estrutura principal

```text
CandidatosTSE/
├── src/main/java/.../controller/   # Rota da página e parâmetros de busca
├── src/main/java/.../service/      # Leitura do CSV e filtros
├── src/main/java/.../model/        # Modelo de candidato
└── src/main/resources/
    ├── data/candidatos/            # CSV usado pela aplicação
    ├── static/css/                 # Estilos da interface
    └── templates/                  # Página Thymeleaf
```
