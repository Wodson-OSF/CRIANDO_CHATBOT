# CRIANDO_CHATBOT (INICIANDO CONVERSA COM CHATBOT)
chat = model.start_chat(history=[])  # Inicia uma nova conversa com o chatbot. O parâmetro `history=[]` indica que não há histórico de conversa anterior.

prompt = input("Esperando prompt: ")  # Solicita ao usuário que digite um prompt (frase inicial para o chatbot).

while prompt != "fim":  # Loop principal da conversa
  response = chat.send_message(prompt)  # Envia o prompt fornecido pelo usuário para o chatbot e obtém a resposta.
  print("Resposta: ", response.text, "\n")  # Imprime a resposta do chatbot para o usuário.

  prompt = input("Esperando prompt: ")  # Solicita novamente um prompt ao usuário para continuar a conversa. O loop encerra quando o usuário digita "fim".
# Melhorando a visualização (Código disponível em https://ai.google.dev/tutorials/python_quickstart#import_packages)

# Importa bibliotecas para formatação e exibição do código
import textwrap
from IPython.display import display
from IPython.display import Markdown

# Função para converter texto em formato Markdown
def to_markdown(text):
  # Substitui marcadores por asteriscos no Markdown
  text = text.replace('•', '  *')
  # Indenta o texto com '> ' para cada linha
  # O predicate garante que todas as linhas sejam indentadas
  return Markdown(textwrap.indent(text, '> ', predicate=lambda _: True))

# Imprime o histórico da conversa
for message in chat.history:
  # Converte a mensagem em formato Markdown
  formatted_message = to_markdown(f'**{message.role}**: {message.parts[0].text}')
  # Exibe a mensagem formatada
  display(formatted_message)
  # Separa as mensagens com uma linha horizontal
  print('-------------------------------------------')
