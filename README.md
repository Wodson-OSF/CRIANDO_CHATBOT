# CRIANDO_CHATBOT (INICIANDO CONVERSA COM CHATBOT)
chat = model.start_chat(history=[])  # Inicia uma nova conversa com o chatbot. O parâmetro `history=[]` indica que não há histórico de conversa anterior.

prompt = input("Esperando prompt: ")  # Solicita ao usuário que digite um prompt (frase inicial para o chatbot).

while prompt != "fim":  # Loop principal da conversa
  response = chat.send_message(prompt)  # Envia o prompt fornecido pelo usuário para o chatbot e obtém a resposta.
  print("Resposta: ", response.text, "\n")  # Imprime a resposta do chatbot para o usuário.

  prompt = input("Esperando prompt: ")  # Solicita novamente um prompt ao usuário para continuar a conversa. O loop encerra quando o usuário digita "fim".
