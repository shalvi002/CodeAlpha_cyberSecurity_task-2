TASK 2: Phishing Awareness Training
import time

# Define sample emails and correct answers
quiz_data = [
    {
        "text": """From: support@bank-secure.com
Subject: Verify your account now!

Dear customer,
We detected unusual activity. Please click the link below to verify your account:
http://bank-secure.verify-info.com""",
        "is_phishing": True
    },
    {
        "text": """From: hr@company.com
Subject: Policy update reminder

Hi team,
Please review the updated HR policies attached to this email.
Best,
HR Department""",
        "is_phishing": False
    },
    {
        "text": """From: IT Support <it-support@company.com>
Subject: Password expired

Your password has expired. Reset now: http://company-secure-reset.com""",
        "is_phishing": True
    },
    {
        "text": """From: newsletter@trustedsource.com
Subject: Weekly tech news

Hello!
Here’s your weekly tech newsletter with curated articles and updates."""
,
        "is_phishing": False
    }
]

def run_quiz():
    score = 0
    print("\n Phishing Awareness Quiz")
    print("Answer each example with Y (phishing) or N (not phishing)\n")

    for idx, item in enumerate(quiz_data, start=1):
        print(f"--- Example {idx} ---")
        print(item["text"])
        answer = input("Is this phishing? (Y/N): ").strip().upper()

        correct = (answer == "Y" and item["is_phishing"]) or (answer == "N" and not item["is_phishing"])
        if correct:
            print(" Correct!\n")
            score += 1
        else:
            print(" Incorrect.")
            print("Explanation: This email is", "phishing." if item["is_phishing"] else "legitimate.")
            print()

        time.sleep(1)

    print(f" Final Score: {score}/{len(quiz_data)}")
 
    print("Thanks for completing the training!\n")

if __name__ == "__main__":
    run_quiz()
    
**OUTPUT:-**
<img width="1052" height="771" alt="Screenshot 2025-12-25 163654" src="https://github.com/user-attachments/assets/7f648323-225b-4b62-bd09-a04e09bb66ab" />
