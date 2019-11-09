# Florianopolis-Wordcloud
!pip install wordcloud -q
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from PIL import Image
from wordcloud import WordCloud, STOPWORDS, ImageColorGenerator

# Create a list of word
text=("Cidade linda, segura em relação as outras capitais.. Praias maravilhosas. Praias bonitas As praias são lindas!!! O verde em contraste com o mar é fabuloso Cordialidade geral e limpeza da cidade. O sul também tem sua beleza, isso é fato! E Floripa demonstra muito bem com suas belas praias, mar limpinho e muitas pessoas bonitas. Cidade limpa, pessoas muito educadas, praias paradisíacas, natureza lindíssima e diversificada. Realmente a Ilha da Magia, tudo de bom. Cidade muita limpa e organizada!!! Praias belíssimas!!!Praias muito bonitas. Visitar as dunas na Lagoa da Conceição e passear de barco são ótimos programas. Vida noturna sempre agitada.Praias e principalmente o povo mais bonito do Brasil! A cidade é limpa, segura, organizada. Gente bonita, belas praias. O passeio na Costa da Lagoa vale muito a pena TUDO, as praias são maravilhosas, o povo muito acolhedor. Cidade linda,pessoas bonitas e acolhedoras,ótimo trânsito e praias muito boas para banho. Florianópolis é linda, as praias são ótimas, com opções pra todos os gostos, desde surfistas até familias com crianças.Local muito Bonito,praias linda e limpas e uma ótima culinária Fiquei apenas um dia na cidade e achei maravilhosa. A paisagem, gente bonita, aquele sotaque do sul... Triste apenas por não ter conhecido nenhuma praia. Organização,pontualidade, postura. Fora a beleza fantástica. Lagoa da Conceição é local incrivel, existe hostel bons, lugar muito bom de sê passar as férias. As paisagens e praias são lindas Cidade linda, belas praias e comida maravilhosa.Excelente infraestrutura praiana, lindas praias, gente bonita, educada, miotas opções de baladas cidade organizada, praias limpas, povo educado, paisagens deslumbrantes. (verão). Ilha da Magia, literalmente!")
 
 # ver quantidade de palavras
print("Quantidade de Palavras: {}".format(len(text)))

# lista de stopword
stopwords = set(STOPWORDS)
stopwords.update(["ótimo", "ótima", "achei", "pena", "também", "um", "gente", "povo", "bem", "mais", "isso", "desde", "muitas", "dia", "nenhuma", "geral", "realmente", "programas", "ter", "muita", "apenas", "bom", "pra", "todos", "Relação", "aquele", "triste", "de", "na", "em", "você", "muito", "tudo", "km", "são", "lá", "sem", "até", "que", "da", "ao", "os", "si", "sao", "nas", "praia", "cidade", "pessoas", "não", "das", "fica", "toma", "coma", "pratos", "como", "principalmente", "dos", "velado", "Ruas", "uma", "simplorios", "existe", "praias", "tem", "torno", "morar", "Lagoa", "Ilha", "Ingleses", "torno", "conta", "alta"])

# gerar uma wordcloud
wordcloud = WordCloud(stopwords=stopwords,
                      background_color="white",
                      width=1600, height=800).generate(text)

# mostrar a imagem final
fig, ax = plt.subplots(figsize=(20,6))
ax.imshow(wordcloud, interpolation='bilinear')
ax.set_axis_off()

plt.imshow(wordcloud);
wordcloud.to_file("airbnb_summary_wordcloud.png")
