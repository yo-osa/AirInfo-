AirInfo: Australian Airline Dashboard
AirInfo is a modern Flask web app that provides real-time flight data and AI-powered insights for Australian airlines. 
It integrates the AviationStack API for live flight information and Google Gemini for generative AI insights, with interactive data visualizations.

 Features
- **Live Flight Data:** Search and display real-time flight information for Australian airlines.
- **AI Insights:** Get demand trends, popular routes, and more using Google Gemini.
- **User-Friendly UI:** Modern, responsive design with animated hero section and dark mode.
- **Data Visualizations:** Bar and pie charts for popular routes, demand periods, and airport stats (matplotlib).
- Custom API Key Input: Users can provide their own AviationStack API key for flight data.

---
Setup & Installation

1. **Clone the repository:**
   ```bash
   git clone <your-repo-url>
   cd airbuddy
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up environment variables:**
   - Only the Google Gemini API key is required in the environment. The AviationStack key is provided by the user at runtime.
   - Create a `.env` file (optional for local dev) or set in your deployment platform:
     ```env
     GEMINI_API_KEY=your_gemini_api_key_here
     # AVIATIONSTACK_API_KEY is optional (user provides it via the form)
     ```

4. **Run locally:**
   ```bash
   python wsgi.py
   # or
   flask run
   ```
   The app will be available at [http://localhost:5000](http://localhost:5000)

---
 Deployment (Render)

1. **Push your code to GitHub.**
2. **Create a new Web Service on [Render](https://render.com/):**
   - Connect your GitHub repo.
   - **Build Command:**
     ```
     pip install -r requirements.txt
     ```
   - **Start Command:**
     ```
     gunicorn wsgi:app
     ```
   - **Environment Variables:**
     - `GEMINI_API_KEY` (required)
     - `AVIATIONSTACK_API_KEY` (optional, leave blank if users provide their own)
   - **No need to set `PORT`**—Render handles this automatically.

---

Usage
1. **Home Page:**
   - Enter origin, destination, and date to view real-time flight data and AI insights.
2. **Scrape Flights:**
   - Enter an Australian airline IATA code and your AviationStack API key to fetch and analyze flights.
   - View AI-generated insights and interactive charts.

---

API Keys
- **Google Gemini:** Get your API key from [Google AI Studio](https://aistudio.google.com/app/apikey).
- **AviationStack:** Get your API key from [AviationStack](https://aviationstack.com/).

---

License
MIT License
CONTACT
For questions or support, see the footer of the app or contact the project maintainer. 
