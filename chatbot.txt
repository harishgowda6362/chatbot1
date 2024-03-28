import random

# Dictionary containing some predefined responses
responses = {
    "hi": ["Hello!", "Hi there!", "Hey!"],
    "how are you": ["I'm good, thanks!", "I'm doing well, thank you!", "All good, thanks for asking!"],
    "bye": ["Goodbye!", "Bye!", "See you later!"],
    "default": ["Sorry, I didn't understand that.", "I'm not sure what you mean.", "Could you please rephrase that?"]
}

def get_response(message):
    # Convert the message to lowercase
    message = message.lower()
    # Check if the message is in the responses dictionary
    if message in responses:
        return random.choice(responses[message])
    else:
        return random.choice(responses["default"])

def main():
    print("Chatbot: Hello! How can I help you?")
    while True:
        user_input = input("You: ")
        if user_input.lower() == 'exit':
            print("Chatbot: Goodbye!")
            break
        response = get_response(user_input)
        print("Chatbot:", response)

if __name__ == "__main__":
    main()