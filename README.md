1. O que é o Padrão DAO? É uma forma de organizar o código onde você separa o Java do SQL.Como funciona: Você cria uma "caixa" (classe) onde só existe código de banco de dados. O resto do programa pede para essa caixa salvar ou buscar dados, sem precisar saber como o SQL funciona.


2. Peças Principais do JDBCConnectionFactory: É a classe responsável por "ligar" o seu Java ao banco MySQL (usando os dados do Laragon).PreparedStatement: É a ferramenta que usamos para rodar o SQL com segurança. Ela evita o SQL Injection (ataques que tentam roubar dados através de comandos maliciosos).ResultSet: É como uma "tabela virtual" que o Java recebe do banco após fazer uma consulta (SELECT).

3. Segurança e OrganizaçãoTry-with-resources: Uma forma de escrever o código que garante que o banco de dados será fechado sozinho quando terminar, evitando que o sistema trave por conexões abertas demais.Tratamento de Erros: Em vez de mostrar erros feios de banco de dados para o usuário, nós criamos uma mensagem padrão (como DbException) para deixar o sistema mais profissional.

4. Estrutura de Pastas (O "Mapa")

model: Onde ficam os objetos (ex: Carro, Cliente).

dao: Onde ficam as interfaces (a lista do que o sistema faz).

dao.impl: Onde o SQL é escrito de verdade.db: Onde fica a conexão.