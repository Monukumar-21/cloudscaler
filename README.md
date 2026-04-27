# AutoScaleOps AI — Google Solutions Challenge 2026

## 🌍 UN Sustainable Development Goals (SDGs) Addressed
* **Goal 9: Industry, Innovation, and Infrastructure:** Building intelligent, resilient, and autonomous cloud infrastructure.
* **Goal 13: Climate Action:** Reducing carbon footprints by minimizing idle server runtime through AI-driven right-sizing and autoscaling.

## 🚀 Overview
AutoScaleOps AI is an agentic Site Reliability Engineering (SRE) prototype that leverages the **Gemini 3.1 Pro** model to autonomously manage cloud scaling decisions. By analyzing real-time server telemetry (CPU utilization, latency, traffic rates, and active pods), the AI acts as a copilot to recommend precise scale-up or scale-down actions. 

This prototype replaces traditional, rigid threshold-based scaling with intelligent, context-aware decision-making—reducing infrastructure costs and preventing Service Level Agreement (SLA) violations.

## ⚙️ How It Works (Input -> AI -> Output)
1. **Input (Telemetry):** The system ingests current cluster metrics including CPU usage, active pods, latency, and queue lengths.
2. **AI Processing:** Gemini API analyzes this state against standard operational playbooks to determine the optimal resource allocation.
3. **Output (Action & Rationale):** The model outputs a strict JSON payload containing:
   - `scale_delta`: How many pods to add/remove.
   - `rationale`: The logical SRE explanation for the action.
   - `cost_impact_usd`: Hourly financial impact.
   - `bottleneck_warning`: Early detection of saturation or anomalies.

## 🛠 Tech Stack
* **Frontend:** React 19, Vite, Tailwind CSS v4, Framer Motion
* **AI Integration:** Google Gemini API (`@google/genai` TypeScript SDK)
* **Design System:** Custom "Clean Minimalism" UI

## 💻 Running the Project Locally
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Create a `.env` file in the root directory and add your Gemini API Key:
   `VITE_GEMINI_API_KEY=your_api_key_here`
4. Run `npm run dev` to start the local development server.

## 🔮 Future Implementations (Next Steps)
* **Kubernetes Webhooks:** Connect the AI output directly to the Kubernetes HPA (Horizontal Pod Autoscaler) to make the scaling fully autonomous.
* **Firebase Auth & Database:** Store historical scaling logs in Firestore and secure the dashboard with Google Auth.
* **Live Cloud Monitoring:** Ingest live telemetry from GCP/Prometheus instead of manual sandbox inputs.
* **Model Fine-Tuning:** Implement RL (Reinforcement Learning) logic to tune Gemini outputs against localized cost constraints.
