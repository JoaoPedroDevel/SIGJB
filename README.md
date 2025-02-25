# Sistema de Inventário em Java

## Passo a Passo para Desenvolvimento

### 1. Definição dos Requisitos
- O sistema deve coletar automaticamente informações do computador, como:
  - Processador
  - Modelo
  - Sistema Operacional
  - Tipo e tamanho do disco
  - Tipo e tamanho da memória RAM
  
- Os seguintes campos serão preenchidos manualmente:
  - Filial
  - Setor
  - Usuário
  - Antivírus
  
- O campo `Status` será definido como "OK" se a coleta for bem-sucedida. Caso contrário, será preenchido manualmente como "Parado".
- O sistema deve registrar a data da última atualização.
- Os dados devem ser armazenados em um banco de dados PostgreSQL/MySQL.
- A interface gráfica será feita em JavaFX.

### 2. Estrutura do Banco de Dados
Criar uma tabela para armazenar as informações do inventário:
```sql
CREATE TABLE inventario (
    id SERIAL PRIMARY KEY,
    filial VARCHAR(255),
    setor VARCHAR(255),
    usuario VARCHAR(255),
    tipo_pc VARCHAR(255),
    processador VARCHAR(255),
    modelo VARCHAR(255),
    sistema_operacional VARCHAR(255),
    tipo_disco VARCHAR(255),
    tipo_memoria VARCHAR(255),
    tamanho_disco VARCHAR(255),
    memoria_ram VARCHAR(255),
    antivirus VARCHAR(255),
    observacao TEXT,
    status VARCHAR(50),
    data_atualizacao TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### 3. Configuração do Projeto
- Criar um projeto Java utilizando Maven.
- Adicionar dependências para:
  - PostgreSQL/MySQL Connector
  - JavaFX
  - JDK 11+

### 4. Implementação
#### 4.1. Criar a Classe `Computador`
- Criar uma classe Java para representar os dados coletados.

#### 4.2. Criar a Classe de Conexão com o Banco de Dados
- Implementar uma classe para gerenciar a conexão JDBC.

#### 4.3. Coleta Automática de Informações
- Utilizar bibliotecas Java para coletar informações do sistema operacional.

#### 4.4. Criar a Interface Gráfica
- Desenvolver a interface para inserção manual de dados e exibição das informações coletadas.

#### 4.5. Implementação da Lógica do Status
- Definir "OK" quando os dados forem coletados automaticamente.
- Permitir edição manual quando necessário.

### 5. Testes e Validações
- Testar em diferentes máquinas para garantir a compatibilidade.
- Validar a integridade dos dados coletados.

### 6. Documentação e Deploy
- Criar um guia de instalação e uso.
- Implementar um mecanismo para atualização do sistema.
