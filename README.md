# **Projeto: Controle de um Braço Robótico com Banco de Dados MySQL**

## **Introdução**

Este relatório descreve a implementação de um sistema de banco de dados para o controle de um braço robótico utilizando MySQL e XAMPP. O projeto foi desenvolvido com o objetivo de armazenar e gerenciar dados essenciais dos seis servomotores responsáveis pela movimentação da mão robótica. As informações coletadas incluem a posição dos motores, a voltagem e a porcentagem da bateria. A integração do sistema foi realizada por meio de um módulo ESP32, conectado a um banco de dados MySQL configurado localmente.

---

## **Banco de Dados: Conceitos e Aplicação no Projeto**

Um banco de dados é uma coleção organizada de informações estruturadas que facilita o armazenamento, acesso e manipulação dos dados. No contexto deste projeto, o banco de dados foi fundamental para garantir o monitoramento eficiente do sistema robótico, permitindo a visualização em tempo real das posições dos servomotores e do status energético. 

### **Estrutura do Banco de Dados**
- Modelo: Relacional.
- Linguagem: SQL.
- Tabelas: Contêm colunas que representam atributos como posição, voltagem e status da bateria.

O banco de dados foi controlado pelo sistema de gerenciamento MySQL, escolhido por:
- Sua robustez.
- Escalabilidade.
- Facilidade de integração com outras tecnologias.

---

## **MySQL: Características e Justificativa da Escolha**

O MySQL é amplamente utilizado devido às seguintes características:
- **Open-Source:** Disponível gratuitamente.
- **Compatibilidade:** Suporta diversos sistemas operacionais e linguagens de programação.
- **Confiabilidade:** Suporte a transações ACID, garantindo integridade dos dados mesmo em casos de falhas.
- **Desempenho:** Capacidade de lidar com múltiplas conexões simultâneas.

Essas propriedades fizeram do MySQL a escolha ideal para o controle dos dados do braço robótico, garantindo estabilidade e eficiência.

---

## **XAMPP: Ambiente de Desenvolvimento Local**

O XAMPP foi escolhido para configurar o ambiente de desenvolvimento local, fornecendo:
- **Servidor Apache.**
- **Banco de Dados MySQL/MariaDB.**
- **PHP e Perl:** Para integração do backend.

### **Vantagens do XAMPP**
1. Facilidade de instalação e configuração.
2. Ambiente completo e integrado para desenvolvimento.
3. Suporte à validação local do sistema antes da implementação final.

---

## **Desenvolvimento do Sistema e Integração**

### **Configuração Local do Banco de Dados**

1. Configuração realizada em uma máquina Lenovo Legion.
2. Porta inicial: **3307**, alterada para **3306** após resolução de conflitos.
3. Usuário root configurado com senha e permissões específicas.

### **Falhas na Conexão Remota**
Devido a erros e bloqueios no MySQL e MariaDB, optou-se por manter o sistema exclusivamente local. Essa decisão eliminou problemas de conectividade remota, garantindo estabilidade na execução dos comandos SQL.

### **Painel de Controle e Monitoramento em Tempo Real**
- Desenvolvido em PHP, com SQL para manipulação de dados.
- Exibição gráfica das informações dos servomotores e status da bateria.
- Interface intuitiva para ajustes operacionais e monitoramento.

---

## **Código de Configuração do Banco de Dados**

Abaixo, o código utilizado para configurar o banco de dados e as tabelas:

```sql
-- Configuração da Porta
port = 3306;

-- Configuração do Usuário
user = ╰(*°▽°*)╯; 
password = (^///^) ;
AllowNoPassword: NO;

-- Acessar o MySQL
mysql -u root -p
todosporcorinthians;

-- Criar o Banco de Dados
CREATE DATABASE braco_robotico;

-- Selecionar o Banco de Dados
USE braco_robotico;

-- Criar a Tabela 'servo_motores'
CREATE TABLE servo_motores (
  id INT AUTO_INCREMENT PRIMARY KEY,
  
  -- Colunas para Motor 1
  voltagem_motor1             DECIMAL(5, 2),
  porcentagem_bateria_motor1  DECIMAL(5, 2),
  posicao_motor1              INT,
  
  -- Colunas para Motor 2
  voltagem_motor2             DECIMAL(5, 2),
  porcentagem_bateria_motor2  DECIMAL(5, 2),
  posicao_motor2              INT,
  
  -- Colunas para Motor 3
  voltagem_motor3             DECIMAL(5, 2),
  porcentagem_bateria_motor3  DECIMAL(5, 2),
  posicao_motor3              INT,
  
  -- Colunas para Motor 4
  voltagem_motor4             DECIMAL(5, 2),
  porcentagem_bateria_motor4  DECIMAL(5, 2),
  posicao_motor4              INT,
  
  -- Colunas para Motor 5
  voltagem_motor5             DECIMAL(5, 2),
  porcentagem_bateria_motor5  DECIMAL(5, 2),
  posicao_motor5              INT,
  
  -- Colunas para Motor 6
  voltagem_motor6             DECIMAL(5, 2),
  porcentagem_bateria_motor6  DECIMAL(5, 2),
  posicao_motor6              INT,

  -- Coluna de Timestamp
  data_hora TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Inserir Dados na Tabela 'servo_motores'
INSERT INTO servo_motores (
  voltagem_motor1, porcentagem_bateria_motor1, posicao_motor1,
  voltagem_motor2, porcentagem_bateria_motor2, posicao_motor2,
  voltagem_motor3, porcentagem_bateria_motor3, posicao_motor3,
  voltagem_motor4, porcentagem_bateria_motor4, posicao_motor4,
  voltagem_motor5, porcentagem_bateria_motor5, posicao_motor5,
  voltagem_motor6, porcentagem_bateria_motor6, posicao_motor6
)
VALUES (
  12.5, 85.0, 90,
  12.4, 80.0, 95,
  12.3, 75.0, 100,
  12.2, 70.0, 105,
  12.1, 65.0, 110,
  12.0, 60.0, 115
);

-- Acessar o MySQL/MariaDB
mysql -u root -p;

-- Listar Bancos de Dados
SHOW DATABASES;

-- Selecionar Banco de Dados
USE braco_robotico;

-- Listar Tabelas
SHOW TABLES;

-- Visualizar Dados
SELECT * FROM servo_motores;

-- Sair do MySQL/MariaDB
EXIT;


Conclusão
A implementação do sistema de banco de dados integrado ao controle do braço robótico foi concluída com sucesso.
Os principais pontos de destaque incluem:

• Estabilidade e eficiência do MySQL para gerenciar dados complexos.
• Facilidade de desenvolvimento local com o XAMPP.
• Interface intuitiva para monitoramento e ajuste dos parâmetros.
• Apesar dos desafios na conexão remota, o sistema local demonstrou ser uma solução prática e confiável,
com potencial de expansão para futuras aplicações.
