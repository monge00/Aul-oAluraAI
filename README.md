# Aul-oAluraAI
Aula de Imersão em AI - Google AI Studio / AI
import requests
import random

url = 'https://raw.githubusercontent.com/guilhermeonrails/api-imersao-ia/main/words.json'
resposta = requests.get(url)
data = resposta.json()
last_value = len(data)-1

valor_secreto = random.choice(data)
palavra_secreta = valor_secreto['palavra']
dica = valor_secreto['dica']
print(f'A palavra secreta tem {len(palavra_secreta)} letras --> {dica}')

resposta_aluno = input('Digite sua resposta: ')
resposta_aluno_minuscula = resposta_aluno.lower()
palavra_secreta_minuscula = palavra_secreta.lower()

if resposta_aluno_minuscula == palavra_secreta_minuscula:
    print('Acertou!')
else:
    print(f'Errou. A resposta correta é {palavra_secreta}')
