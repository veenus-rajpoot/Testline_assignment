# Quiz Performance Analysis and Personalized Recommendations

## Project Overview
This project analyzes quiz performance data to generate personalized recommendations for students. By leveraging historical and current quiz data, the solution identifies weak areas, computes topic-wise accuracy, and provides actionable insights to help students improve their preparation.

## Features
- **Performance Analysis**: Calculates overall and topic-wise accuracy.
- **Insights Generation**: Highlights weak areas and suggests improvement strategies.
- **Personalized Recommendations**: Provides actionable steps to strengthen preparation.
- **Visualization**: Includes graphical representations of performance trends.
- **API Integration**: Serves recommendations and insights via a REST API.

---

## Setup Instructions
### Prerequisites
1. Python 3.7 or higher.
2. Required libraries:
   - `pandas`
   - `matplotlib`
   - `seaborn`
   - `flask`

### Installation
1. Clone the repository from GitHub:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Place your data files (`current_quiz.json`, `quiz_submission.json`, `historical_quiz.json`) in the project directory.

4. Run the script:
   ```bash
   python quiz_analysis.py
   ```

5. Access the API locally at `http://127.0.0.1:5000/recommendations`.

---

## Project Structure
```
|-- quiz_analysis.py          # Main script
|-- requirements.txt          # List of required Python libraries
|-- current_quiz.json         # Sample current quiz data
|-- quiz_submission.json      # Sample quiz submission data
|-- historical_quiz.json      # Sample historical quiz data
|-- response_distribution.png # Generated visualization
```

---

## Approach Description
### Step 1: Data Exploration
- Loaded JSON data for current quiz, quiz submissions, and historical quizzes.
- Flattened and normalized nested structures (e.g., response maps) into Pandas DataFrames for analysis.

### Step 2: Generate Insights
- Computed overall accuracy using correct and total answers.
- Grouped historical data by topic to calculate topic-wise accuracy.
- Visualized response distribution and weak areas using bar plots.

### Step 3: Personalized Recommendations
- Suggested improvement areas based on weak topics and low accuracy.
- Prioritized foundational topics for users with low overall scores.

### Step 4: Study Plan
- Generated a study plan, assigning daily practice tasks for weak topics.

### Step 5: Persona Identification
- Classified users into personas (`High Performer`, `Steady Learner`, or `Beginner`) based on accuracy trends.

### Step 6: API Integration
- Built a REST API using Flask to serve recommendations and study plans.

---

## Example API Response
```json
{
  "accuracy": 80.0,
  "persona": "Steady Learner",
  "recommendations": [
    "Practice more questions on Body Fluids and Circulation.",
    "Focus on foundational topics to build confidence."
  ],
  "study_plan": {
    "Body Fluids and Circulation": "Practice 5 questions daily"
  }
}
```

---

## Screenshots
### Visualization
![Response Distribution](response_distribution.png)

---

## Future Enhancements
1. Add support for more detailed analytics, such as difficulty-level trends.
2. Incorporate machine learning to predict student improvement trajectories.
3. Provide multi-language support for broader accessibility.

---

## License
This project is licensed under the MIT License. See the LICENSE file for details.
