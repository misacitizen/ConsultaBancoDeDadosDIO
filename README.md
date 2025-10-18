🎯 Consultas SQL Realizadas
Foram solicitadas 12 consultas distintas para análise dos dados. Todas as consultas estão contidas no arquivo Consultas_Desafio_Filmes.sql e são detalhadas abaixo.

1. Nome e Ano dos Filmes
Objetivo: Buscar o nome e o ano de todos os filmes.

SQL

SELECT
    Nome,
    Ano
FROM
    Filmes;
2. Filmes Ordenados por Ano
Objetivo: Buscar o nome e o ano dos filmes, ordenados por ordem crescente pelo ano.

SQL

SELECT
    Nome,
    Ano
FROM
    Filmes
ORDER BY
    Ano ASC;
3. Detalhes de um Filme Específico
Objetivo: Buscar pelo filme "De Volta para o Futuro", trazendo o nome, ano e a duração.

SQL

SELECT
    Nome,
    Ano,
    Duracao
FROM
    Filmes
WHERE
    Nome = 'De Volta para o Futuro';
4. Filmes Lançados em 1997
Objetivo: Buscar os filmes lançados especificamente em 1997.

SQL

SELECT
    Nome
FROM
    Filmes
WHERE
    Ano = 1997;
5. Filmes Lançados Após 2000
Objetivo: Buscar os filmes lançados APÓS o ano 2000.

SQL

SELECT
    Nome
FROM
    Filmes
WHERE
    Ano > 2000;
6. Filmes por Intervalo de Duração
Objetivo: Buscar os filmes com a duração maior que 100 e menor que 150, ordenando pela duração em ordem crescente.

SQL

SELECT
    Nome,
    Duracao
FROM
    Filmes
WHERE
    Duracao > 100
    AND Duracao < 150
ORDER BY
    Duracao ASC;
7. Quantidade de Filmes por Ano
Objetivo: Buscar a quantidade de filmes lançadas por ano, agrupando por ano e ordenando pelo ano em ordem decrescente.

SQL

SELECT
    Ano,
    COUNT(*) AS Quantidade
FROM
    Filmes
GROUP BY
    Ano
ORDER BY
    Ano DESC;
8. Atores do Gênero Masculino
Objetivo: Buscar os Atores do gênero masculino, retornando o PrimeiroNome e UltimoNome.

SQL

SELECT
    PrimeiroNome,
    UltimoNome
FROM
    Atores
WHERE
    Genero = 'M';
9. Atores do Gênero Feminino Ordenados
Objetivo: Buscar os Atores do gênero feminino, retornando o PrimeiroNome e UltimoNome, e ordenando pelo PrimeiroNome.

SQL

SELECT
    PrimeiroNome,
    UltimoNome
FROM
    Atores
WHERE
    Genero = 'F'
ORDER BY
    PrimeiroNome ASC;
10. Nome do Filme e seu Gênero
Objetivo: Buscar o nome do filme e todos os seus gêneros.

SQL

SELECT
    T1.Nome AS Filme,
    T3.Genero
FROM
    Filmes AS T1
INNER JOIN
    FilmesGenero AS T2 ON T1.Id = T2.IdFilme
INNER JOIN
    Generos AS T3 ON T2.IdGenero = T3.Id;
11. Filmes do Gênero "Mistério"
Objetivo: Buscar o nome do filme que possui o gênero do tipo "Mistério".

SQL

SELECT
    T1.Nome
FROM
    Filmes AS T1
INNER JOIN
    FilmesGenero AS T2 ON T1.Id = T2.IdFilme
INNER JOIN
    Generos AS T3 ON T2.IdGenero = T3.Id
WHERE
    T3.Genero = 'Mistério';
12. Nome do Filme e Elenco (Ator e Papel)
Objetivo: Buscar o nome do filme e os atores, trazendo o PrimeiroNome, UltimoNome e seu Papel no filme.

SQL

SELECT
    T1.Nome AS Filme,
    T3.PrimeiroNome,
    T3.UltimoNome,
    T2.Papel
FROM
    Filmes AS T1
INNER JOIN
    ElencoFilme AS T2 ON T1.Id = T2.IdFilme
INNER JOIN
    Atores AS T3 ON T2.IdAtor = T3.Id
ORDER BY
    T1.Nome;
