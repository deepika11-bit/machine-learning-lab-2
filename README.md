https://dev.to/idsulik/empowering-newbies-building-confidence-through-600-leetcode-solutions-a-guide-for-beginners-3960

https://medium.com/@koheiarai94/60-leetcode-questions-to-prepare-for-coding-interview-8abbb6af589e

https://medium.com/@austin-starks/heres-the-secret-to-getting-good-at-leetcode-that-nobody-ever-told-you-43a6d4852a44


https://www.geeksforgeeks.org/machine-learning/naive-bayes-classifiers/


Googliness & Leadership Interview
This round was focused on behavioral assessment, leadership traits, and cultural fit (often referred to as “Googliness”).

Here’s a sample of the types of questions I was asked (paraphrased):

Share a complex, technically challenging project you worked on.
Talk about a time when you gave constructive feedback that had a lasting impact.
How do you prioritize user needs in your work? Share an example.
Tell me about a time you came up with an innovative solution and its impact.
Share a failure, how you identified it, and how you responded.
If a teammate tries to take undue credit for a group project, how would you handle it?
How do you resolve disagreements between team members with different technical opinions?
What’s your approach to breaking down and distributing complex tasks?
Tips for Aspirants
If you’re preparing for big tech interviews:

Focus as much on clarity of thought as you do on coding.
Be ready to ask clarifying questions and explore edge cases out loud.
Don’t jump into coding, focus on running down the optimal solution clearly first.
And remember — even if you don’t get in, the learning you gain is yours to keep.






🧩 The Final Interview
The next round was scheduled for 17th July with a Senior Software Engineer (12+ years of experience).
He presented a hard Dynamic Programming problem — and unfortunately, I couldn’t solve it.

Within a few days, I received the rejection mail.

💭 Reflections and Takeaways
No, I didn’t make it to Google.
But I made it through something far more valuable — the journey that taught me what true growth feels like.

Here are my biggest takeaways:

🌱 1. Preparation is not just about solving problems — it’s about building patience.
Hours of revision and practice don’t just sharpen your skills; they prepare your mind to stay calm when things go wrong — even during a power cut.

💡 2. Rejection doesn’t define your capability — it defines your current version.
Not clearing an interview doesn’t mean you’re not good enough. It simply means your “version 1.0” isn’t ready yet. Keep upgrading yourself.

🔥 3. Confidence isn’t built by success — it’s built by surviving failure.
The moment you bounce back after a tough round, that’s when you truly start believing in yourself.

⚙️ 4. Luck plays a role, but preparation decides how much luck can help you.
Some days things won’t go your way — the key is to stay ready for the next opportunity that does.

🚀 5. Getting close to your dream counts.
Even though I didn’t crack Google, getting that far reminded me that my hard work, projects, and consistency are taking me in the right direction.

That experience didn’t give me an offer letter — but it gave me a stronger mindset, a clearer sense of direction, and the belief that I’ll make it there someday.





Step 3: LeetCode Practice – The Right Way
If you want to get a job at companies like Facebook and Google, you’ll want to be proficient at solving most leetcode questions. That means not only being able to solve them, but doing so optimally.

Get Austin Starks’s stories in your inbox
Join Medium for free to get updates from this writer.

Enter your email
Subscribe

Remember me for faster sign in

The questions you’ll need to know how to solve is colloquially known as “The Blind 75”. It’s a list of the most important leetcode questions to study. Download this sheet and approach it exactly as follows:

Rules of Engagement
Start with a category you’ve studied.
Set a timer for 20 minutes.
Aim to solve the problem. If you don’t know the best solution, try to solve first by brute force, then analyzing its strengths and weaknesses. If you know how to solve the problem optimally, do so.
Stop when the timer goes off. Period.
Look up the most optimal solution. Google, YouTube, and ChatGPT can be invaluable for this. Feel free to take notes and draw pictures to help it sink into your brain.
Looking at the solution (or some notes that you took), input the optimal solution into leetcode.
On the Excel sheet, if you got the problem right in 20 minutes or less, mark “Yes”. If you didn’t, mark “No”. Use an array (like the first example) to track how many times you attempted to solve the problem.
Take a 10 minute break, and do another problem.
Complexity Coverage
Don’t just settle for the first solution you find. Analyze its time and space complexities and think about potential optimizations. This will prepare you for the high-level complexities that come up in interviews at places like Google and Facebook.

Iterative Learning
The next day, revisit the problems you got wrong.
Set a 20-minute timer again.
Repeat the above song and dance.
Why this approach? It’s simple. When studying leetcode, it’s tempting to spend an hour on an individual problem, especially if you’re close to the solution or you think you should know it. But spending an exorbitant amount of time on one question is detrimental, particularly with the quantity of problems you want to solve. Your aim is to get good at a wide array of problems, not just one or two.

So there you have it – a foolproof plan to mastering LeetCode. It requires time, effort, and above all, the right strategy. With this approach, you’re not just solving problems; you’re mastering them. And soon enough, you’ll be the one getting those offers from top tech companies.




data.csv

"Outlook","Temperature","Humidity","Windy","Play Golf"
Rainy,Hot,High,False,No
Rainy,Hot,High,True,No
Overcast,Hot,High,False,Yes
Sunny,Mild,High,False,Yes
Sunny,Cool,Normal,False,Yes
Sunny,Cool,Normal,True,No
Overcast,Cool,Normal,True,Yes
Rainy,Mild,High,False,No
Rainy,Cool,Normal,False,Yes
Sunny,Mild,Normal,False,Yes
Rainy,Mild,Normal,True,Yes
Overcast,Mild,High,True,Yes
Overcast,Hot,Normal,False,Yes
Sunny,Mild,High,True,No

import pandas as pd

# Load the CSV file into a DataFrame
df = pd.read_csv('data.csv')

# View the first 5 rows of your data
df.head()


# 1. Define Prior Probabilities
p_yes_prior = 9 / 14
p_no_prior = 5 / 14

# 2. Define Conditional Probabilities based on the user data
# Format: P(Feature_Value | Class)
p_sunny_given_yes = 2 / 9
p_hot_given_yes = 2 / 9
p_normal_given_yes = 6 / 9
p_false_given_yes = 6 / 9

p_sunny_given_no = 3 / 5
p_hot_given_no = 2 / 5
p_normal_given_no = 1 / 5
p_false_given_no = 2 / 5

# 3. Calculate Joint Likelihood (Posterior numerators)
# X = (Sunny, Hot, Normal, False)
p_yes_today = p_sunny_given_yes * p_hot_given_yes * p_normal_given_yes * p_false_given_yes * p_yes_prior
p_no_today = p_sunny_given_no * p_hot_given_no * p_normal_given_no * p_false_given_no * p_no_prior

# 4. Normalize the Probabilities
total_prob = p_yes_today + p_no_today
p_yes_normalized = p_yes_today / total_prob
p_no_normalized = p_no_today / total_prob

# 5. Output Results and Final Prediction
print(f"Posterior Probability (Yes): {p_yes_normalized:.3f}")
print(f"Posterior Probability (No): {p_no_normalized:.3f}")

if p_yes_normalized > p_no_normalized:
    print("Final Prediction: Yes (Play Golf)")
else:
    print("Final Prediction: No (Don't Play Golf)")
