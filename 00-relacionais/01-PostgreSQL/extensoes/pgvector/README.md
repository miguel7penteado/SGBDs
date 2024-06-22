# Extensão PGVECTOR

## Extensão do SGBD Postgres para Base de dados Vetoriais

### Repositório no github
[pgvector no GitHub](https://github.com/Azure-Samples/azure-postgres-pgvector-python)

### Instalação no MS-Windows 10 rodando o SGBD Postgresql versão 15

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

E execute construtor do código fonte. O Visual Studio vai compilar tudo para você.

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
