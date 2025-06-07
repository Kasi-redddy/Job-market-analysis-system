# Job-market-analysis-system

Welcome! This project is all about making sense of job descriptions by automatically picking out and classifying the skills they mention. With this API, you can quickly see which skills are well-established in your dataset and which ones are just starting to trend. It’s built with Python and FastAPI, and designed to run smoothly in Google Colab. You’ll get a public URL for easy sharing and testing, thanks to ngrok.

---

## Why This Project?

Ever wondered which skills pop up most often in job listings, or which new buzzwords are on the rise? This API helps you answer those questions in a snap. Whether you’re a student, researcher, or HR professional, you’ll find it handy for analyzing real-world job data.

---

## What Can It Do?

- Scan job descriptions and pull out relevant skills from a customizable list.
- Show you which skills are “established” (popular) and which are “emerging” (on the rise), based on your dataset.
- Assign a trend score to each detected skill.
- Provide a simple REST API you can use in your own apps or notebooks.
- Offer a user-friendly Swagger UI at `/docs` for interactive testing.
- Export all results to a CSV file for further analysis or reporting.

---

## Getting Started in Google Colab

1. **Upload your dataset:**  
   Make sure your file is named `dataset.csv` and includes at least these columns: `job_description_text` and `seniority_level`.

2. **Set up ngrok securely:**  
   Before you run the app, set your ngrok authtoken like this:
   import os
os.environ["NGROK_AUTHTOKEN"] = "your-ngrok-authtoken-here"

3. **Run the notebook cells:**  
The code will guide you through data cleaning, skill extraction, and launching the API.

4. **Grab your public API link:**  
Once the server is running, you’ll see a public URL in the output. Use it to access the API or visit `/docs` for the Swagger UI.

5. **Try it out:**  
Here’s a quick test you can run:
import requests
url = "https://<your-ngrok-url>/skill-trend-detector"
payload = {"job_description": "Looking for a Senior ML Engineer with Python, TensorFlow, MLOps, AWS, and leadership experience."}
response = requests.post(url, json=payload)
print(response.json())

---

## API Details

- **Endpoint:** `POST /skill-trend-detector`
- **Request:**  
{
"job_description": "Your job description here"
}
- **Response:**  
{
"detected_skills": [
{"skill": "python", "category": "established", "trend_score": 0.89},
...
]

} 
- **Swagger UI:**  
Check out `/docs` on your public ngrok URL for an interactive experience.

---

## Exporting Results

Want to see all detected skills for every job description? No problem. The code lets you save everything to a CSV file called `all_detected_skills.csv`—perfect for sharing or further analysis.

---

## Good Practices

- **Keep your ngrok authtoken private.** Don’t upload it to GitHub—use environment variables instead.
- **Check your dataset for missing values** before running the analysis.
- **Review the results:** The skill list is customizable, so feel free to tweak it for your needs.

---

## License

This project is intended for academic and educational use.

---

## Need Help?

If you have questions, suggestions, or run into any issues, feel free to open an issue or reach out to the maintainer. Happy skill hunting!
 
