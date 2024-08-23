# DIO - Trilha .NET - Banco de Dados🗄️

Este repositório contém as soluções para o desafio de banco de dados da trilha .NET da DIO, utilizando SQL Server. O objetivo do desafio é realizar 12 consultas SQL para recuperar informações específicas sobre filmes, atores e gêneros.

## 📑Descrição do Projeto

O projeto consiste em um banco de dados SQL Server contendo informações sobre filmes🎥, atores🎭, gêneros⚧️ e suas relações. 

![Diagrama banco de dados](Imagens/diagrama.png)

## Realização do Desafio

- Criação do banco de dados com o script presente na pasta Scripts deste repositório. 
- Realização dos comandos referente as 12 consultas do desafio, que podem ser verificados abaixo ou no arquivo de Respostas deste repositório, contendo o código SQL para cada consulta.


## 📤📥Consultas 

## 1 - Buscar o nome e ano dos filmes:

![Exercicio 1](Imagens/1.png)

### Resposta:
SELECT Nome, Ano FROM Filmes

## 2 - Buscar o nome e ano dos filmes, ordenados por ordem crescente pelo ano

![Exercicio 2](Imagens/2.png)

### Resposta: 
SELECT Nome, Ano, Duracao FROM Filmes
ORDER BY Ano

## 3 - Buscar pelo filme de volta para o futuro, trazendo o nome, ano e a duração

![Exercicio 3](Imagens/3.png)

### Resposta: 
SELECT Nome, Ano, Duracao FROM Filmes
WHERE Nome = 'De Volta para o Futuro'

## 4 - Buscar os filmes lançados em 1997

![Exercicio 4](Imagens/4.png)

### Resposta: 
SELECT Nome, Ano, Duracao FROM Filmes
WHERE Ano = 1997

## 5 - Buscar os filmes lançados APÓS o ano 2000

![Exercicio 5](Imagens/5.png)

### Resposta:
SELECT Nome, Ano, Duracao FROM Filmes
WHERE Ano LIKE '2%'


## 6 - Buscar os filmes com a duracao maior que 100 e menor que 150, ordenando pela duracao em ordem crescente

![Exercicio 6](Imagens/6.png)

### Resposta: 
SELECT Nome, Ano, Duracao FROM Filmes
WHERE Duracao > 100 AND Duracao < 150
ORDER BY Duracao ASC

## 7 - Buscar a quantidade de filmes lançadas no ano, agrupando por ano, ordenando pela duracao em ordem decrescente

![Exercicio 7](Imagens/7.png)

### Resposta:
SELECT Ano, COUNT(*) Quantidade FROM Filmes
GROUP BY Ano
ORDER BY Quantidade DESC

## 8 - Buscar os Atores do gênero masculino, retornando o PrimeiroNome, UltimoNome

![Exercicio 8](Imagens/8.png)

### Resposta: 
SELECT * FROM Atores
WHERE Genero = 'M'

## 9 - Buscar os Atores do gênero feminino, retornando o PrimeiroNome, UltimoNome, e ordenando pelo PrimeiroNome

![Exercicio 9](Imagens/9.png)

### Resposta: 
SELECT * FROM Atores
WHERE Genero = 'F'
ORDER BY PrimeiroNome

## 10 - Buscar o nome do filme e o gênero

![Exercicio 10](Imagens/10.png)

### Resposta:
SELECT Filmes.Nome, Generos.Genero 
FROM Filmes
INNER JOIN FilmesGenero ON Filmes.Id = FilmesGenero.IdFilme
INNER JOIN Generos ON Generos.Id = FilmesGenero.IdGenero

## 11 - Buscar o nome do filme e o gênero do tipo "Mistério"

![Exercicio 11](Imagens/11.png)

### Resposta: 
SELECT Filmes.Nome, Generos.Genero
FROM Filmes INNER JOIN FilmesGenero ON Filmes.Id = FilmesGenero.IdFilme
INNER JOIN Generos ON Generos.Id = FilmesGenero.IdGenero
WHERE Generos.Genero = 'Mistério'

## 12 - Buscar o nome do filme e os atores, trazendo o PrimeiroNome, UltimoNome e seu Papel

![Exercicio 12](Imagens/12.png)

### Resposta:
SELECT Filmes.Nome, Atores.PrimeiroNome, Atores.UltimoNome, ElencoFilme.Papel
FROM Filmes INNER JOIN ElencoFilme ON Filmes.Id = ElencoFilme.IdFilme
INNER JOIN Atores ON Atores.Id = ElencoFilme.IdAtor


## ✨Conclusão
Este projeto foi uma excelente oportunidade para consolidar o conhecimento sobre banco de dados, SQL e relacionamentos entre tabelas. As consultas realizadas demonstraram a flexibilidade e o poder da linguagem SQL para extrair informações específicas de um banco de dados.



