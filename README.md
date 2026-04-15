# Math-quiz
import random

def math_quiz():
    score = 0
    
    print(" Welcome to Math Quiz Game\n")
    
    print("Choose Difficulty Level:")
    print("1. Easy")
    print("2. Medium")
    print("3. Hard")
    
    level = input("Enter choice (1/2/3): ")
    
    for i in range(5):  # 5 questions
        if level == "1":
            num1 = random.randint(1, 10)
            num2 = random.randint(1, 10)
            op = random.choice(["+", "-"])
        
        elif level == "2":
            num1 = random.randint(10, 50)
            num2 = random.randint(1, 20)
            op = random.choice(["+", "-", "*"])
        
        elif level == "3":
            num1 = random.randint(10, 100)
            num2 = random.randint(1, 50)
            op = random.choice(["+", "-", "*", "/"])
        
        else:
            print("Invalid level ")
            return
        
        # Question display
        print(f"\nQ{i+1}: {num1} {op} {num2} = ?")
        
        # Correct answer calculate
        if op == "+":
            correct = num1 + num2
        elif op == "-":
            correct = num1 - num2
        elif op == "*":
            correct = num1 * num2
        else:
            correct = round(num1 / num2, 2)
        
        # User answer
        try:
            user = float(input("Your answer: "))
            
            if user == correct:
                print("Correct ")
                score += 1
            else:
                print(f"Wrong  Correct answer: {correct}")
        
        except:
            print("Invalid input ")

    # Final Score
    print(f"\n Final Score: {score}/5")
    
    if score == 5:
        print("Excellent ")
    elif score >= 3:
        print("Good ")
    else:
        print("Practice more ")

math_quiz()









