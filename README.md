<h3 align="center">Hospedando um site estático na AWS S3</h3>


## 🧐 Sobre <a name="Sobre"></a>


O projeto tem como intuito mostrar que a AWS S3 (Simple Storage Serve), não apenas armazena objetos, mas também pode hospedar um site completamnete estático feito em HTML, CSS e JavaScript e assim aproveitarmos a escalabilidade e disponilidade que a AWS oferece.

Lembrando que a AWS oferece um nível gratuito no S3, onde podemos usar para hospedar nosso site sem custos até 5GB e para criar um website é uma quantidade razoável.


## Tecnologias usadas
- HTML / CSS / JavaScript
  
  
## Etapas da criação na AWS
- Criação de um bucket;
- Upload dos arquivos dentro do bucket;
- A verificação das informações do arquivo index.html;
- Configurando para que a URL gerada pela AWS se torne pública;
- Configuração para que o bucket de armazenamento comum se torne um de site e,
- Definições de permissões e configurações de segurança para o bucket se torna público.

Na política do bucket, foi colocado um código JSON, que é uma configuração ideal para um website, pois permite que o acesso seja feito sem que alguém altere o seu conteúdo.

```bash
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::estaticoawss3/*"
            ]
        }
    ]
}

```

🚀 Site disponível em uma URL na internet 

<img width="700" alt="Imagem2" src="https://github.com/fariasangelica/site_estatico_aws/assets/98922466/7cf171c9-ee19-44ba-a875-6e701282e936">

## Configurando o controle de versionamento do site
O controle de versão não é habilitado por padrão quando criamos um bucket, então foi feita a configuração para que todas as vezes que o site por atualizado, ele mantenha o arquivo original.


## Etapas da configuração do versionamento
Ir em propriedades > Versionamento de bucket > Ativar o versionamento

Título do site antes da atualização do arquivo index.html: 

<img width="362" alt="image" src="https://github.com/fariasangelica/site_estatico_aws/assets/98922466/fac9d5a0-cd8c-43a1-a7ec-2fe3a8b40745">

Site após a alteração do arquivo index.html:

<img width="362" alt="image" src="https://github.com/fariasangelica/site_estatico_aws/assets/98922466/e551401a-b41a-4595-88d6-5bbc3bf95a78">


Atualização do versionamento na AWS:

<img width="700" alt="Imagem4" src="https://github.com/fariasangelica/site_estatico_aws/assets/98922466/40e99d1d-b8f6-4ecb-89e2-91e3781d393c">

## 📊 Resultado final do layout do site estático <a name="Site disponível"></a>

http://estaticoawss3.s3-website.us-east-2.amazonaws.com/

<img width="700" alt="Imagem3" src="https://github.com/fariasangelica/site_estatico_aws/assets/98922466/715326ed-5471-44b7-ad2b-16c32bb16b59">



## ✍️ Autora <a name="author"></a>

- Angelica Farias - https://www.linkedin.com/in/angelica-farias/

## 📌 Conhecimento guiado por: <a name="author"></a>

- Universidade Global
