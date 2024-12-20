# Quiz-Application
Quiz Application
import random

# State and define the quiz question and answers
quiz = {
    1: {"question": "What has keys but can't open locks?", "answer": "piano"},
    2: {"question": "What is full of holes but still holds water?", "answer": "sponge"},
    3: {"question": "What begins with T, ends with T, and has T in it?", "answer": "teapot"},
    4: {"question": "What can travel around the world while staying in a corner?", "answer": "stamp"}
}
#Taking the user's name first.
def run_quiz():
    """Run the quiz application."""
    user_name = input("Please enter your name: ").strip()
    if not user_name:
        print("Name cannot be empty. Please restart the quiz and enter a valid name.")
        return
#setting Initial Score to Zero 
    score = 0
    total_questions = len(quiz)
    question_ids = list(quiz.keys())
    random.shuffle(question_ids)

    print(f"\nWelcome to the Creative Logic Quiz, {user_name}!")
    print("Answer the following questions:")

    for i in question_ids:
        print("\n" + quiz[i]['question'])
        user_answer = input("Your answer: ").strip()

        if user_answer.lower() == quiz[i]['answer'].lower():
            print("Correct!")
            score += 1
        else:
            print(f"Wrong! The correct answer is '{quiz[i]['answer']}'.")

    # Declare scores at the end
    print(f"\n{user_name}, your final score is {score} out of {total_questions}.")

    # Provide feedback based on score
    if score == total_questions:
        print("Excellent! You got all the answers right!")
    elif score >= total_questions / 2:
        print("Good job! You passed the quiz.")
    else:
        print("Keep practicing! You'll get better.")

if __name__ == "__main__":
    run_quiz()
