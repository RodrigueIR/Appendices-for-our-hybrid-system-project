# Early Outbreak Detection Using AI + Social Media
## A hybrid model for faster pandemic response
##### Detect disease outbreaks ~5 days earlier than traditional systems
## The problem we’re trying to solve
When someone catches Ebola, they might feel sick and tweet about it within 3–5 days. But official reports take 10–14 days. By then, the disease has already spread.

This project asks: what if we could use those early tweets to warn health officials before an outbreak explodes?

We built a system that: Reads tweets with AI to find real symptom mentions (not jokes or news), Feeds those signals into a disease model (SEIR) to predict where and when an outbreak will grow, Alerts humans days before traditional methods
# Does it actually work?
Yes. We tested it on the 2014–2015 Ebola outbreak using 10,457 tweets.
- Our AI catches 87 out of 100 symptom tweets (87.3% recall)
- Hybrid model reduces prediction error by 71% (from 7-day delay to 2 days)
- 5 days earlier detection on average compared to official reports

We also tested on Zika and COVID-19. It worked well after ~6–10 hours of keyword tuning (94% accuracy).
Here’s the dashboard output from one of our runs:
<img width="974" height="608" alt="image" src="https://github.com/user-attachments/assets/e6c4b2ad-42f6-4773-8430-47e1e70dadf5" />
(the outbreak detection dashboard or forecast comparison graph)
Example: symptom tweet volume spiking 5 days before official reports
# How the system works (simply)
### Tweets → Clean text → AI finds symptom mentions → Daily symptom counts → SEIR model → Outbreak alert
The whole thing runs on a regular computer (8GB RAM, standard CPU). No expensive hardware needed.
# What’s in this repo (the appendices explained)
We’ve included everything you need to understand, replicate, or adapt the project.
### 📄 IRB approval
This confirms the research followed ethical guidelines. We only used public tweets, no personal or identifiable information. The project was reviewed and approved by USIU-Africa’s ethics committee.
### 📊 Dataset
We used publicly available tweets from the 2014–2015 Ebola outbreak (thanks to Karry Harsh on kaggle). The dataset contains 10,457 tweets with categories like symptoms, news, prevention, and unrelated content. Only 4.3% were symptom-related – which is exactly why you need AI to find the signal in the noise.
### 💻 Project demo (code)
This Jupyter notebook contains the full working code:
- Text cleaning and preprocessing
- TF-IDF vectorization
- Logistic Regression classifier (chosen for speed + explainability)
- SEIR model integration
- SHAP explainability charts
- Dashboard visualizations

You can run it yourself to see how we got 87.3% recall and 5-day early warnings.
### 💰 Budget and work plan
A realistic breakdown for deploying this in a real health department:
- Year 1 total cost: $111,320 (less than hiring two epidemiologists)
- Staff: part-time tech + epidemiologist + 5 hrs/week tweet labeling
- ROI: $2.59 back for every $1 invested in year 1
- 12-month rollout plan (setup → pilot → live monitoring → evaluation)
## Limitations (real talk)
We’re not claiming this is perfect. Here’s what doesn’t work yet:
- English only – misses French, Arabic, local languages where outbreaks happen
- Twitter only – doesn’t see Facebook, WhatsApp, or offline conversations
- Metaphors confuse the AI – “this traffic gave me a fever” gets flagged as a symptom (42% of false alarms)
- Never tested on a live outbreak – all validation used historical data
That said, the system is ready for a pilot with human oversight. An epidemiologist reviews alerts before any action is taken.
## Why this matters
Five days doesn’t sound like much. But in an outbreak, five days means:
- Hospitals can stock supplies before the rush
- Contact tracers can find exposed people before they spread it further
- Communities get warnings while they still have time to prepare
Research shows interventions started 4–7 days earlier can reduce peak outbreak size by 20–40%. In a 1,000-case outbreak, that’s 200–400 people who don’t get sick.
##### That’s what this project is about.
## Built with
- Python + Jupyter
- Scikit-learn (Logistic Regression, TF-IDF)
- Pandas, Seaborn, Matplotlib
- SHAP for explainability
- Streamlit for dashboard (prototype)
## Let’s connect
This was my undergraduate research project at USIU-Africa (Spring 2026). If you’re working on disease surveillance, infoveillance, or AI for public health; I’d love to hear from you.

### Rodrigue Irampa
LinkedIn: www.linkedin.com/in/rodrigue-irampa-9056001a1

“Social media, when properly filtered through AI, can help save lives by detecting disease outbreaks before they spiral out of control.”
