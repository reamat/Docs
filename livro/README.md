# Padrões para os livros colaborativos

## Licença
Este trabalho está licenciado sob a Licença Creative Commons Atribuição-CompartilhaIgual 3.0 Não Adaptada. Para ver uma cópia desta licença, visite <https://creativecommons.org/licenses/by-sa/3.0/> ou envie uma carta para Creative Commons, PO Box 1866, Mountain View, CA 94042, USA.

## Sobre o código fonte
O código fonte está escrito em [Latex](https://latex-project.org/) e as referências bibliográficas em [BibTex](http://www.bibtex.org/), testado em computador Linux com o pacote [TexLive](http://www.tug.org/texlive/). O texto está em formatação **utf-8**.

## Compilando

### Em computador Linux
O código LaTeX está testado em computador [Linux](https://pt.wikipedia.org/wiki/Linux) com o pacote [TexLive](https://www.tug.org/texlive/) instalado. O livro pode ser compilado com:

    $ make

Isto gera o livro em formato PDF (main.pdf). Também, o código pode ser compilado em formato DVI:

    $ make dvi

Alguma vezes a compilação pode gerar erros devido a incompatibilidade com antigos arquivos temporários. Para limpar os arquivos temporários gerados durante a compilação, digite:

    $ make clean

Alternativamente, o livro pode ser compilado com os comandos usuais `latex main`, `bibtex main`, `pdflatex main`, `makeindex main`. Lembrando que `main.tex` é o arquivo LaTeX principal.

#### Formato HTML
O livro também pode ser compilado em formato HTML, digitando:

	$ make html

Este comando cria a pasta `./html` onde todo os arquivos da versão HTML do livro são colocados.

- EPUB:

		$ make epub

Este comando cria o arquivo `main.epub` contendo o livro em formato EPUB.

### Outros sistemas operacionais

O código LaTeX pode ser compilado em outros sistemas operacionais.

Em primeiro lugar, deve-se editar o arquivo de configuração `config.knd`. Este arquivo contém instruções TeX para controlar o formato e a versão do livro. Por exemplo, para setar o formato do livro em PDF, garanta que este arquivo contenha o seguinte texto:

    \isbooktrue \ishtmlfalse

Por fim, o livro pode ser compilado com a seguinte sequência de comandos:

    pdflatex main
    bibtex main
    makeindex main
    pdflatex main
    pdflatex main
