# Mendix Voice

Experimentos com IA Generativa usando voz.

Este é um projeto simples criado para ajudar a começar com integração de voz. Ele inclui um módulo Mendix chamado RetellAI, que é a tecnologia que usamos para converter voz em texto, enviar para um LLM e converter a resposta de volta para voz.

Este vídeo mostra como criar uma conta no RetellAI (é gratuito e fácil). Configure seu agente de voz e obtenha as chaves necessárias (API Key e Agent Key) para usar no projeto.

### Algumas observações:
- Neste exemplo, mantivemos as coisas bem simples e não implementamos agendamento de calendário ou chamadas de API para o Mendix.
- O calendário é muito fácil de configurar no agente RetellAI, mas você precisará de uma conta no Cal.com.


### Avançado:
- Para implementar chamadas de API do Mendix usando funções, será necessário publicar a API REST do Mendix em um ambiente pago para que a chamanda possa ser acessada na Internet. Na pasta "Custom Functions", incluí a implementação que demonstramos durante a apresentação para Salvar Metas. Os componentes da pasta "Custom Functions" foram excluídos do projeto (apenas para referência/ajuda).
- Você também precisará configurar um Custom Function no RetellAI. Abaixo, estamos incluindo o JSON usado no RetellAI, que corresponde aos recursos encontrados na pasta “Custom Functions”.

```
{
  "output": {
    "type": "object",
    "properties": {
      "success": {
        "type": "boolean",
        "description": "Verdadeiro se a meta de econômica foi atualizada com sucesso, caso contrário, Falso."
      }
    }
  },
  "type": "object",
  "properties": {
    "SavingGoalName": {
      "type": "string",
      "description": "O nome da meta de economia."
    },
    "SavingGoalTargetAmount": {
      "type": "number",
      "description": "O valor que você está almejando para sua meta de economia."
    },
    "SavingGoalCurrentAmount": {
      "type": "number",
      "description": "O valor atual economizado para a meta."
    }
  },
  "required": [
    "SavingGoalName",
    "SavingGoalTargetAmount",
    "SavingGoalCurrentAmount"
  ]
}
```