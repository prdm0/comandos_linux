# Comandos de Linux úteis

+ Instalando o LaTeX: `sudo pacman -S texlive-bibtexextra texlive-core texlive-fontsextra texlive-humanities texlive-langextra texlive-latexextra texlive-pictures texlive-publishers texlive-science texstudio`

+ Convertendo uma imagem para um tamanho fixo: `convert example.png -resize 200×100 example.png`  

+ Adicionando chave não oficial: `gpg --recv-keys`

+ Reduzindo tamanho de arquivos PDF: `gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/screen -dNOPAUSE -dQUIET -dBATCH -sOutputFile=resultado.pdf original.pdf`

+ Extraindo páginas de um arquivo PDF: `gs -sDEVICE=pdfwrite -dNOPAUSE -dBATCH -dSAFER -dFirstPage=1 -dLastPage=1 -sOutputFile=title.pdf paper_JSCS.pdf`

+ Medindo velocidade da internet no terminal: s`peedtest-cli ou speedtest-cli --share` 

+ Pesquisando no recursivamente em arquivos PDF's: `pdfgrep -HiR 'Gauss' /home/pedro/Dropbox/UFPB/`

+ Aumentando o áudio acima de 100%: `pulseaudio-ctl up 10`. Isso amplifica 10% em cima do volume máximo. Use `down` para baixar.

### Configurando warsaw para acesso aos bancos:

Inicialmente devemos instalar o **warsaw-bin** que encontra-se nos repositórios comunitários fazendo`yaourt -S warsaw-bin --noconfirm`. Depois, devemos configurar o serviço para que seja inicializado com a inicialização do sistema: `systemctl enable warsaw.service` e `systemctl start warsaw.service`.


### Baixando vídeos do youtube

+ Verificando os formatos: `youtube-dl -F link_do_video`

+ Convertendo no formato escolhido: `youtube-dl -f 22 link_do_video`

### Impressão via Terminal:

+ `lpq`: Ver fila de impressão.
+ `lprm -`: Limpa toda a fila de impressão de uma só vez.
+ `lpstat -p -d`: Conhecer o nome da impressora.
+ `lp -d nomedaimpressora /endereço/do/documento`: Imprindo por outra impressora que não seja padão.
+ `lp -n 2 documento.txt`: Imprimir duas cópias.
+ `lp -P 1,3 documento.txt`: Imprimir páginas 1 e 3 do documento.
+ `lp -P 1-3 documento.txt`: Imprimir das páginas 1 a 3 do documento.
+ `lp -d npdoc -o sides=two-sided-long-edge documento.txt`: Imprimindo em ambos os lados.
+ `lp -d npdoc -o sides=two-sided-long-edge media=letter documento.txt`: Imprimindo em ambos os lados no formato carta.

### Usando o pacman:

+ `sudo pacman -Sy` = sincroniza os repositórios.
+ `sudo pacman -Su` = procura por atualização.
+ `sudo pacman -Syu` = sincroniza os repositórios/procura por atualização.
+ `sudo pacman -Syy` = sincroniza os repositórios do Manjaro Linux.
+ `sudo pacman -Syyu` = sincronização total/procura por atualização.
+ `sudo pacman -S pacote` = instala um pacote.
+ `sudo pacman -R pacote` = remove um pacote.
+ `sudo pacman -Rs pacote` = remove o pacote junto com as dependências não usadas por outros pacotes.
+ `sudo pacman -Rsn pacote` = remove o pacote junto com as dependências não usadas por outros pacotes e junto com os arquivos de configuração.
+ `sudo pacman -Ss pacote` = procura por um pacote.
+ `sudo pacman -Sw pacote` = apenas baixa o pacote e não o instala.
+ `sudo pacman -Si pacote` = mostra informações de um pacote não instalado.
+ `sudo pacman -Qi pacote` = mostra informações do pacote já instalado.
+ `sudo pacman -Se pacote` = instala apenas as dependências.
+ `sudo pacman -Ql pacote` = mostra todos os arquivos pertencentes ao pacote.
+ `sudo pacman -Qu` = mostra os pacotes que serão atualizados.
+ `sudo pacman -Q` = lista todos os pacotes instalados.
+ `sudo pacman -Qo arquivo` = mostra a qual pacote aquele arquivo pertence.
+ `sudo pacman -Qdt` = lista pacotes desnecessários, sem dependências
+ `sudo pacman -Rns $(pacman -Qqdt)` = apaga pacotes desnecessários, sem dependências
+ `sudo pacman -A pacote.pkg.tar.gz` = instala um pacote local.
+ `sudo pacman -Sc` = deleta do cache todos os pacotes antigos.
+ `sudo pacman -Scc` = limpa o cache, removendo todos os pacotes existentes no /var/cache/pacman/pkg/.
+ `sudo pacman-optimize` = otimiza a base de dados do pacman.
+ `sudo pacman -Sdd` = instala ignorando as dependências.
+ `sudo pacman -Rdd` = elimina um pacote ignorando as dependências.
+ `sudo pacman-mirrors.conf` = para gerenciar pacman.cof
+ `sudo pacman-mirrors -g` = para gerar um novo mirrorlist
+ `sudo pacman -U home/user/arquivo.tar.xz` = instalar pacotes baixados no pc
+ `sudo pacman -U http://www.site.com/arquivo.tar.xz` = instalar pacotes baixados via download
+ `sudo pacman -Qem` = lista pacotes instalados do repo AUR
+ `sudo pacman -Rscn` = desinstala pacotes e suas dependencias e seus registros, tudo.
+ `sudo pacman -S pacote –noconfirm` = Instala o pacote sem precisar confirmar com “yes/no ,S/N”…
+ `sudo pacman -Syu –ignoregroup pacote1 , pacote2…` = sincroniza os repositórios/procura por atualização e ignora os grupos dos pacotes solicitados
`sudo pacman-mirrors -g` = rankeia as mirros de acordo com velocidades.
`yaourt -Syua –devel` = sincronizar a base de dados
`yaourt -Syyuua` = atualizar o repo AUR
`yaourt -Ss nome` = pesquisar no repo AUR
`yaourt -S nome` = instalar pacotes do repo AUR
`yaourt -R nome` = remover pacotes do repo AUR
`yaourt -Rsn nome` = remover pacotes + dependências do repo AUR
`yaourt -Syu –devel –aur` = sincronizar a base de dados e atualiza pacotes

## Endereços de DNS

A Level 3 é uma empresa gigantesca que fornece serviços de conectividade para milhares de outras empresas ao redor do mundo. Aqui no Brasil, por exemplo, a GVTa utiliza para conectar seus clientes ao mundo. Ela cuida da infraestrutura do Google Public DNS, mas tem seu próprio serviço. Você pode usar uma combinação dos seguintes endereços:

```
    Servidor principal primário: 209.244.0.3;
    Servidor principal secundário: 209.244.0.4;
    Servidor alternativo: 4.2.2.1;
    Servidor alternativo: 4.2.2.2;
    Servidor alternativo: 4.2.2.3;
    Servidor alternativo: 4.2.2.4;
    Servidor alternativo: 4.2.2.5;
    Servidor alternativo: 4.2.2.6.
```

Todos eles respondem a partir dos Estados Unidos.

