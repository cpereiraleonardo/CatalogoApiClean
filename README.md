# Catalogo


Para fazer o migrattions no console do Nuget é necessário usar o comando abaixo:
>add-migration cargaIncial -project Catalogo.Infrastructure

Onde "cargaInicial" é o nome indicado para identificar o Migration.


Foi necessário o arquivo program.cs adicionando a linha:
>//Fazendo a conexão com o banco de dados e inserido no Context para executar acessos ao banco de dados.
builder.Services.AddDbContext<ApplicationDbContext>(options =>
options.UseMySql(mySqlConnection,
ServerVersion.AutoDetect(mySqlConnection),
x => x.MigrationsAssembly("Catalogo.Infrastructure")));

Me basei no artigo:

https://learn.microsoft.com/pt-br/ef/core/managing-schemas/migrations/projects?tabs=dotnet-core-cli
