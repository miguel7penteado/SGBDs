# Extensão PGVECTOR

## Extensão do SGBD Postgres para Base de dados Vetoriais

### Antes de começar
Você precisa ter instalado no seu windows

- PostgreSQL (versão 15 ou superior)
- GIT for windows
- Visual Studio (profissional ou comunidade) com o Visual C++ ativado (usei a versão 2022, mas o Visual Studio 2019 deve servir também).

Esse é o link do Repositório no github do projeto [pgvector no GitHub](https://github.com/Azure-Samples/azure-postgres-pgvector-python).

### Preparando o ambiente para compilar o código fonte

Abra uma janela do Prompt de comando (janela do "DOS") e siga as instruções abaixo:

Configure as **variáveis de ambiente C++** relativas ao Visual Studio 2022 de linha de comando. O Visual Studio ofere o arquivo de lotes **vcvarsx86_amd64.bat** para te ajudar a fazer isso.
```cmd
cd "C:\Program Files\Microsoft Visual Studio\2022\Professional\VC\Auxiliary\Build"
vcvarsx86_amd64.bat
```

Configure a **variáveis de ambiente PGROOT** na linha de comando de compilação e construção para o arquivo de construção do pgvector possa encontrar sua instalação do PostgreSQL 15.
```cmd
set "PGROOT=c:\PROGRA~1\PostgreSQL\15"
```

Configure as variáveis de ambiente do GIT for windows na linha de comando de compilação e construção.
```cmd
set PATH=C:\Progra~1\Git\bin;%PATH%
set PATH=C:\Progra~1\Git\usr\bin;%PATH%
```

Baixe o repositório do pgvector do github no diretório temporário
```cmd
cd %TMP%
git clone --branch v0.7.2 https://github.com/pgvector/pgvector.git
```

Agora entre do diretório que você baixou o código fonte
```cmd
cd %TMP\pgvector%
```

E execute construtor do código fonte com a boa e velha ferramenta NMAKE. O compilador cl do Visual C++ vai compilar tudo para você.

```cmd
C:\Users\COMPUT~1\AppData\Local\Temp\pgvector>nmake /F Makefile.win

Microsoft (R) Program Maintenance Utility Versão 14.40.33808.0
Direitos autorais da Microsoft Corporation. Todos os direitos reservados.

        copy sql\vector.sql sql\vector--0.7.2.sql
        1 arquivo(s) copiado(s).
		
        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\bitutils.c /Fosrc\bitutils.obj bitutils.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\bitvec.c /Fosrc\bitvec.obj bitvec.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\halfutils.c /Fosrc\halfutils.obj halfutils.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\halfvec.c /Fosrc\halfvec.obj halfvec.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\hnsw.c /Fosrc\hnsw.obj hnsw.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\hnswbuild.c /Fosrc\hnswbuild.obj hnswbuild.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\hnswinsert.c /Fosrc\hnswinsert.obj hnswinsert.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\hnswscan.c /Fosrc\hnswscan.obj hnswscan.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\hnswutils.c /Fosrc\hnswutils.obj hnswutils.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\hnswvacuum.c /Fosrc\hnswvacuum.obj hnswvacuum.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\ivfbuild.c /Fosrc\ivfbuild.obj ivfbuild.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\ivfflat.c /Fosrc\ivfflat.obj ivfflat.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\ivfinsert.c /Fosrc\ivfinsert.obj ivfinsert.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\ivfkmeans.c /Fosrc\ivfkmeans.obj ivfkmeans.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\ivfscan.c /Fosrc\ivfscan.obj ivfscan.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\ivfutils.c /Fosrc\ivfutils.obj ivfutils.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\ivfvacuum.c /Fosrc\ivfvacuum.obj ivfvacuum.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\sparsevec.c /Fosrc\sparsevec.obj sparsevec.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast /c src\vector.c /Fosrc\vector.obj vector.c

        cl /nologo /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32_msvc" /I"c:\PROGRA~1\PostgreSQL\15\include\server\port\win32" /I"c:\PROGRA~1\PostgreSQL\15\include\server" /I"c:\PROGRA~1\PostgreSQL\15\include"   /O2 /fp:fast src\bitutils.obj src\bitvec.obj src\halfutils.obj src\halfvec.obj src\hnsw.obj src\hnswbuild.obj src\hnswinsert.obj src\hnswscan.obj src\hnswutils.obj src\hnswvacuum.obj src\ivfbuild.obj src\ivfflat.obj src\ivfinsert.obj src\ivfkmeans.obj src\ivfscan.obj src\ivfutils.obj src\ivfvacuum.obj src\sparsevec.obj src\vector.obj "c:\PROGRA~1\PostgreSQL\15\lib\postgres.lib" /link /DLL /OUT:vector.dll    

		Criando biblioteca vector.lib e objeto vector.exp

```

### Instalação a moda antinga: "NMAKE INSTALL"

Você agora vai instalar as bibliotecas dentro da pasta de instalação do seu PostgreSQL versão 15. Quem vai fazer isso para você é a ferramenta NMAKE.
Era assim que funcionava antigamente antes da popularização das ferramentas de Entrega de Pacotes, vulgo instaladores.

(Não preciso lembrar que para você conseguir fazer isso, seu ambiente com as variáveis que definimos acima deve ser de ADMINISTRADOR. Caso contrário o NMAKE não terá permissão de escrita na pasta do PostgreSQL).

```cmd
C:\Users\COMPUT~1\AppData\Local\Temp\pgvector>nmake /f Makefile.win install

Microsoft (R) Program Maintenance Utility Versão 14.31.31104.0
Direitos autorais da Microsoft Corporation. Todos os direitos reservados.

        copy vector.dll "C:\Program Files\PostgreSQL\15\lib"
        1 arquivo(s) copiado(s).

        copy vector.control "C:\Program Files\PostgreSQL\15\share\extension"
        1 arquivo(s) copiado(s).

        copy sql\vector--*.sql "C:\Program Files\PostgreSQL\15\share\extension"
sql\vector--0.1.0--0.1.1.sql
sql\vector--0.1.1--0.1.3.sql
sql\vector--0.1.3--0.1.4.sql
sql\vector--0.1.4--0.1.5.sql
sql\vector--0.1.5--0.1.6.sql
sql\vector--0.1.6--0.1.7.sql
sql\vector--0.1.7--0.1.8.sql
sql\vector--0.1.8--0.2.0.sql
sql\vector--0.2.0--0.2.1.sql
sql\vector--0.2.1--0.2.2.sql
sql\vector--0.2.2--0.2.3.sql
sql\vector--0.2.3--0.2.4.sql
sql\vector--0.2.4--0.2.5.sql
sql\vector--0.2.5--0.2.6.sql
sql\vector--0.2.6--0.2.7.sql
sql\vector--0.2.7--0.3.0.sql
sql\vector--0.3.0--0.3.1.sql
sql\vector--0.3.1--0.3.2.sql
sql\vector--0.3.2--0.4.0.sql
sql\vector--0.4.0--0.4.1.sql
sql\vector--0.4.1--0.4.2.sql
sql\vector--0.4.2--0.4.3.sql
sql\vector--0.4.3--0.4.4.sql
sql\vector--0.4.4--0.5.0.sql
sql\vector--0.5.0--0.5.1.sql
sql\vector--0.5.1--0.6.0.sql
sql\vector--0.6.0--0.6.1.sql
sql\vector--0.6.1--0.6.2.sql
sql\vector--0.6.2--0.7.0.sql
sql\vector--0.7.0--0.7.1.sql
sql\vector--0.7.1--0.7.2.sql
sql\vector--0.7.2.sql
       32 arquivo(s) copiado(s).
	   
       mkdir "C:\Program Files\PostgreSQL\15\include\server\extension\vector"
       
	   for %f in (src\halfvec.h src\sparsevec.h src\vector.h) do copy %f "C:\Program Files\PostgreSQL\15\include\server\extension\vector"

C:\Users\COMPUT~1\AppData\Local\Temp\pgvector>copy src\halfvec.h "C:\Program Files\PostgreSQL\15\include\server\extension\vector"
        1 arquivo(s) copiado(s).

C:\Users\COMPUT~1\AppData\Local\Temp\pgvector>copy src\sparsevec.h "C:\Program Files\PostgreSQL\15\include\server\extension\vector"
        1 arquivo(s) copiado(s).

C:\Users\COMPUT~1\AppData\Local\Temp\pgvector>copy src\vector.h "C:\Program Files\PostgreSQL\15\include\server\extension\vector"
        1 arquivo(s) copiado(s).
```

Feito !

## Brincando um pouco com sua nova extensão:

```sql
-- ativando a exensão do banco de dados
CREATE EXTENSION vector;

-- criando a sua tabela. Vamos chama-la de meus-vetores
-- A coluna que vai armazenar os vetores se chama, por exemplo, embedding. Sugestivo.

CREATE TABLE  "meus-vetores" 
(
   id        bigserial PRIMARY KEY, 
   embedding vector(3)
);

-- Vamos colocar dois vetores tridimensionais dentro da tabela meus-vetores
INSERT   INTO "meus-vetores" (embedding) VALUES ('[1,2,3]'), ('[4,5,6]');

-- Obtenha os vizinhos mais próximos pela distância L2
SELECT * FROM "meus-vetores" ORDER BY embedding <-> '[3,1,2]' LIMIT 5;

/*
Esta estensão também suporta:

 produto interno    <#> 
 distância cosseno (<=>) 
 distância L1      (<+>  OBS: esse operador foi adicionado a partir da versão 0.7.0 da extensão

Nota: O produto interno <#> retorna o produto interno negativo, pois o Postgres suporta apenas varreduras de índice de pedidos ASC em operadores

*/


```



