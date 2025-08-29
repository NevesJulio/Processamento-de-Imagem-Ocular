# Processamento e categorização de imagens oculares.
Esse projeto conciste em todo o processo de segmentação, redimensionamento, processamento e 
categorização de um banco de dados de retinopatia diabética. Ou seja, esse projeto descreve 
todos os passos de pegar um banco de dados bruto de retinopatia diabética de imagens com e 
sem diabetes até o passo de ter um algorítmo de categorização de paciente diabético e não 
diabéticos.

## Funcionalidades

- Pegar todos os dados da pasta DataSet e salvar em uma pasta dataset_selecionado com duas pastas separadas em duas categorias de 400 imagens cada, com retinopatia diabética(with_DR) e sem retinopatia diabética (no_DR).
- Depois pegar esses dados e separar em duas pastas, redimensionados em 128x128 pixels e 256x256 pixels, resized_128 e resized_256 respectivamente cada uma com as imagens com e sem RD separadas em duas pastas with_DR e no_DR.
- Criar as pastas clahe_128 e clahe_256 com as imagens de redimensionadas após passarem por um processo de equalizaçõa de histograma, com o objetivo de melhorar o contraste das imagens, também separas nas mesmas pastas com e sem RD.
- Dentro dessas pastas foram criadas pastas sobel_128 e sobel_256 que foram colocadas as imagens que estão nessas pastas depois do algorítmo de clahe passados por um filtro sobel para identificação de bordas.


## Estrutura dos arquivos

DataSet/  
└── [imagens originais]

dataset_selecionado/  
├── with_DR/ # 400 imagens com retinopatia diabética  
└── no_DR/ # 400 imagens sem retinopatia diabética  

resized_128/  
├── with_DR/ # Imagens com RD redimensionadas para 128x128  
└── no_DR/ # Imagens sem RD redimensionadas para 128x128  

resized_256/  
├── with_DR/ # Imagens com RD redimensionadas para 256x256  
└── no_DR/ # Imagens sem RD redimensionadas para 256x256  
    
clahe_128/  
├── with_DR/ # Imagens 128x128 com RD após CLAHE  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── Sobel_128/ # Imagens 128x128 com RD após CLAHE + filtro Sobel  
└── no_DR/ # Imagens 128x128 sem RD após CLAHE  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── Sobel_128/ # Imagens 128x128 sem RD após CLAHE + filtro Sobel  

clahe_256/  
├── with_DR/ # Imagens 256x256 com RD após CLAHE  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── Sobel_256/ # Imagens 256x256 com RD após CLAHE + filtro Sobel  


└── no_DR/ # Imagens 256x256 sem RD após CLAHE  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── Sobel_256/ # Imagens 256x256 sem RD após CLAHE + filtro Sobel  

Training/  
├── MLP/ #Notebooks e outputs referêntes ao Multilayer Layer perceptron  
├──  knn/ #Notebooks e outputs referêntes ao k nearest neighbors  
├── arvore_decisao/ #Notebooks e outputs referêntes a arvore de decisão  
└── naive_bayes/ #Notebooks e outputs referêntes ao Naive Bayes  
