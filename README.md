import re

# Function to process user input and give responses
def chatbot_response(user_input):
    # Convert input to lowercase for easier matching
    user_input = user_input.lower()
    
    # Simple if-else statements to match user input
    if "hi" in user_input or "hello" in user_input:
        return "Hello! How can I help you today?"
    elif "how are you" in user_input:
        return "I'm just a bot, but I'm doing fine, thank you!"
    elif "your name" in user_input or "who are you" in user_input:
        return "I am a simple chatbot created to help you with basic queries."
    elif "bye" in user_input or "goodbye" in user_input:
        return "Goodbye! Have a great day!"
    elif "thanks" in user_input or "thank you" in user_input:
        return "You're welcome!"
    elif re.search(r'\b(what|who|where|why|how)\b', user_input):  # Simple question matching
        return "I'm not sure about that, but I can help with other things."
    else:
        return "Sorry, I didn't understand that. Can you ask something else?"

# Main function to start the chat
def start_chat():
    print("Chatbot: Hello! Type 'bye' to exit.")
    
    while True:
        user_input = input("You: ")
        response = chatbot_response(user_input)
        print(f"Chatbot: {response}")
        
        if 'bye' in user_input.lower() or 'goodbye' in user_input.lower():
            break

# Start the chatbot
if __name__ == "__main__":
    start_chat()

