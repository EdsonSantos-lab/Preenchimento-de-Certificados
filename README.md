# Projeto: Automação de Emissão de Certificados
Descrição:
Este projeto automatiza a criação de certificados personalizados para participantes de cursos, lendo informações de uma planilha Excel e gerando arquivos de imagem individuais. Ele combina Python, Pandas e Pillow (PIL) para criar certificados de forma rápida e profissional.

Funcionalidades Implementadas:
Leitura de dados do Excel

Importa a planilha planilha_alunos.xlsx contendo informações dos participantes:

Nome

Nome do curso

Tipo de participação

Data de início e término

Carga horária

Data de emissão do certificado

python
Copiar
Editar
import pandas as pd
lista_alunos = pd.read_excel('planilha_alunos.xlsx')
Manipulação de imagens com Pillow

Abre um modelo de certificado (certificado_padrao.jpg) para cada participante.

Utiliza a classe ImageDraw para adicionar textos sobre a imagem.

Diferentes fontes e tamanhos são usados para destacar campos importantes, como o nome do participante e o curso.

python
Copiar
Editar
from PIL import Image, ImageDraw, ImageFont
imagem = Image.open('certificado_padrao.jpg')
desenha = ImageDraw.Draw(imagem)
fonte_nome = ImageFont.truetype('tahomabd.ttf', 90)
Geração automática de certificados personalizados

Para cada linha da planilha, insere os dados do participante nos locais corretos do certificado.

Campos como datas e carga horária são destacados em cores específicas.

Cada certificado é salvo com nome único combinando índice e nome do participante.

python
Copiar
Editar
imagem.save(f'{linha}_{nome}_Certificado.jpg')
Benefícios do Projeto:
Redução de trabalho manual: Gera centenas de certificados automaticamente.

Personalização completa: Cada certificado recebe o nome, curso e dados específicos do participante.

Flexibilidade: Fácil adaptação para diferentes layouts de certificados ou planilhas.

Profissionalismo: Usa fontes e cores específicas para destacar informações importantes.
