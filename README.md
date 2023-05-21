 # Programação de Software Básico - Trabalho I
#### 03/2023 

 ## 1 Introdução 
 
O trabalho da disciplina consiste em implementar um programa que realiza zoom em imagens, com resolução de sub-pixel. Para isso, uma imagem será utilizada como entrada e deverá ser gerada como saída uma imagem com um zoom de três vezes, contendo pixels amplificados compostos apenas por sub-pixels puramente vermelhos, verdes, azuis e pretos.
A imagem de entrada deve ser uma imagem colorida com precisão de 24 bits por pixel (R, G, B), onde cada componente possui um valor de intensidade de 0 a 255. Para a manipulação de imagens, está sendo fornecida uma biblioteca que permite ler e escrever imagens no formato PPM (Portable Pix Map). 

 ## 2 Funcionamento 
 
  Para cada pixel da imagem de entrada, após o processo de zoom, será gerada uma matriz de sub-pixels que podem apenas estar ligados em função de sua respectiva cor (vermelho, verde, azul), ou desligados (preto). A matriz utilizada é organizada com um arranjo de três colunas e três linhas, contendo as cores vermelho, verde e azul, nessa ordem, como ilustra o exemplo [A]  [A] As bordas escuras são apresentadas apenas a título ilustrativo.:
figure figures/subpixel.png
Figura 2.1 Exemplo de subpixels
Cada sub-pixel pode apenas estar ligado ou desligado, dessa forma será necessário reduzir a precisão das cores da imagem de entrada e utilizar diferentes padrões de sub-pixel para ter-se quatro níveis de brilho. Para cada pixel da imagem de entrada, devem ser gerados os seguintes padrões:

    Para níveis de cor de 0 a 74, todos os sub-pixels devem ser pretos;
    Para níveis de cor de 75 a 134, o sub-pixel do meio deve ser da cor respectiva (R, G ou B) e os outros dois devem ser pretos;
    Para níveis de cor de 135 a 179, o sub-pixel do meio deve ser preto e os outros dois devem ser da cor respectiva (R, G ou B);
    E para níveis de cor de 180 a 255, todos os sub-pixels devem ser de sua cor respectiva.
    
Antes             |  Depois
:-------------------------:|:-------------------------:
![Antes](lena.ppm)  |  ![Depois](nicolodi.ppm)


## Como ler o Projeto

#### 1. Clone the repository
git clone https://github.com/<username>/cs50w-network.git 
  
#### 2. Navigate to the project directory
cd cs50w-network
  
#### 3. Compile
mingw32-make (Windows)
make (Linux) 
  
#### 4. Executar
 ./zoom - Executa o código, lê a imagem de entrada no diretório e gera a imagem de saída, em PPM
  
