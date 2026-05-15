import React, { useMemo, useState } from "react";
import { createRoot } from "react-dom/client";
import { motion } from "framer-motion";
import {
  Search,
  Sparkles,
  CheckCircle2,
  FileText,
  MapPin,
  UserRound,
  Briefcase,
  WalletCards,
  GraduationCap,
  Building2,
  HeartPulse,
  ArrowRight,
  RotateCcw,
  Database,
  Cloud,
  ShieldCheck
} from "lucide-react";
import "./styles.css";

const benefitPrograms = [
  {
    id: 1,
    name: "Reskilling for Mid-Career Workers",
    category: "Training & Career",
    tags: ["training", "career", "jobseeker", "worker", "mid-career", "age40plus"],
    ageMin: 40,
    ageMax: 65,
    income: ["B40", "M40", "T20"],
    suitableFor: ["Jobseeker", "Employee", "Retiree", "Business Owner"],
    description:
      "Supports adults who want to learn new digital or career skills for better employability or career transition.",
    documents: ["MyKad copy", "Latest resume", "Employment status declaration", "Training interest form"],
    steps: [
      "Choose a preferred training area",
      "Prepare identification and resume",
      "Submit interest form",
      "Attend screening or briefing",
      "Begin training programme"
    ]
  },
  {
    id: 2,
    name: "Digital Skills Training Grant",
    category: "Education & Upskilling",
    tags: ["training", "education", "digital", "career", "jobseeker", "student"],
    ageMin: 18,
    ageMax: 60,
    income: ["B40", "M40"],
    suitableFor: ["Student", "Jobseeker", "Employee"],
    description:
      "Helps eligible Malaysians join digital skills courses such as AI, cloud, data, coding, and digital marketing.",
    documents: ["MyKad copy", "Income declaration", "Education certificate", "Course selection form"],
    steps: [
      "Select digital course",
      "Check eligibility",
      "Upload supporting documents",
      "Submit application",
      "Wait for approval notification"
    ]
  },
  {
    id: 3,
    name: "SME Digitalisation Support",
    category: "Business & Digitalisation",
    tags: ["business", "sme", "digital", "grant", "fintech", "productivity"],
    ageMin: 18,
    ageMax: 75,
    income: ["B40", "M40", "T20"],
    suitableFor: ["Business Owner"],
    description:
      "Supports small businesses that want to adopt digital tools, online sales, automation, or cloud systems.",
    documents: ["MyKad copy", "SSM registration", "Business bank statement", "Digitalisation proposal"],
    steps: [
      "Identify business digital need",
      "Prepare SSM and bank documents",
      "Choose approved digital solution",
      "Submit application",
      "Implement approved solution"
    ]
  },
  {
    id: 4,
    name: "B40 Family Support Aid",
    category: "Financial Aid",
    tags: ["financial", "family", "aid", "b40", "parent"],
    ageMin: 21,
    ageMax: 75,
    income: ["B40"],
    suitableFor: ["Parent", "Jobseeker", "Employee", "Retiree"],
    description:
      "Provides basic financial support for low-income households with priority for families and dependents.",
    documents: ["MyKad copy", "Household income proof", "Bank account statement", "Dependent information"],
    steps: [
      "Check household income category",
      "Prepare income documents",
      "Fill application form",
      "Submit bank details",
      "Track application status"
    ]
  },
  {
    id: 5,
    name: "Senior Citizen Wellness Support",
    category: "Healthcare & Wellness",
    tags: ["health", "senior", "wellness", "retiree"],
    ageMin: 60,
    ageMax: 90,
    income: ["B40", "M40"],
    suitableFor: ["Retiree"],
    description:
      "Assists senior citizens with basic wellness screening, healthcare awareness, and selected support services.",
    documents: ["MyKad copy", "Medical record if available", "Income declaration", "Emergency contact details"],
    steps: [
      "Confirm age eligibility",
      "Prepare identification",
      "Select nearest support centre",
      "Book screening or appointment",
      "Follow up on recommended care"
    ]
  },
  {
    id: 6,
    name: "Women Entrepreneur Starter Grant",
    category: "Business Funding",
    tags: ["business", "women", "grant", "entrepreneur", "fintech"],
    ageMin: 18,
    ageMax: 65,
    income: ["B40", "M40"],
    suitableFor: ["Business Owner"],
    description:
      "Helps women-led microbusinesses start or expand through small funding, mentoring, and business guidance.",
    documents: ["MyKad copy", "Business profile", "SSM registration if available", "Simple business plan"],
    steps: [
      "Prepare business summary",
      "Collect identification and business proof",
      "Submit application",
      "Attend interview if required",
      "Use funds based on approved plan"
    ]
  },
  {
    id: 7,
    name: "Youth Career Upskilling Programme",
    category: "Youth & Career",
    tags: ["youth", "career", "training", "jobseeker", "student"],
    ageMin: 18,
    ageMax: 35,
    income: ["B40", "M40"],
    suitableFor: ["Student", "Jobseeker"],
    description:
      "Supports young Malaysians with employability skills, interview preparation, digital training, and job placement exposure.",
    documents: ["MyKad copy", "Education certificate", "Resume", "Career interest form"],
    steps: [
      "Complete profile assessment",
      "Select career pathway",
      "Submit resume",
      "Join training session",
      "Attend job matching activity"
    ]
  },
  {
    id: 8,
    name: "Single Parent Assistance Programme",
    category: "Family Support",
    tags: ["family", "parent", "financial", "aid", "b40"],
    ageMin: 21,
    ageMax: 70,
    income: ["B40", "M40"],
    suitableFor: ["Parent"],
    description:
      "Provides guidance and selected assistance for single parents who need family, income, or employment support.",
    documents: ["MyKad copy", "Children/dependent details", "Income proof", "Supporting family status document"],
    steps: [
      "Confirm parent/dependent details",
      "Prepare income documents",
      "Submit application",
      "Attend verification if required",
      "Receive support decision"
    ]
  }
];

const initialForm = {
  age: "50",
  state: "Selangor",
  status: "Employee",
  income: "M40",
  need: "training",
  role: "Employee"
};

const needs = [
  { value: "training", label: "Training / Reskilling", icon: GraduationCap },
  { value: "financial", label: "Financial Aid", icon: WalletCards },
  { value: "business", label: "Business Support", icon: Building2 },
  { value: "health", label: "Healthcare", icon: HeartPulse },
  { value: "career", label: "Career Support", icon: Briefcase }
];

function scoreProgram(program, form) {
  const age = Number(form.age || 0);
  let score = 0;
  const reasons = [];

  if (age >= program.ageMin && age <= program.ageMax) {
    score += 25;
    reasons.push(`Age ${age} fits the programme range.`);
  }

  if (program.income.includes(form.income)) {
    score += 20;
    reasons.push(`${form.income} income profile is accepted.`);
  }

  if (program.suitableFor.includes(form.role) || program.suitableFor.includes(form.status)) {
    score += 25;
    reasons.push(`Suitable for ${form.role.toLowerCase()} profile.`);
  }

  if (program.tags.includes(form.need)) {
    score += 25;
    reasons.push(`Matches your main need: ${form.need}.`);
  }

  if (age >= 40 && program.tags.includes("age40plus")) {
    score += 10;
    reasons.push("Strong match for mid-career reskilling.");
  }

  return { ...program, score: Math.min(score, 100), reasons };
}

function Badge({ children }) {
  return <span className="badge">{children}</span>;
}

function Card({ children, className = "" }) {
  return <div className={`card ${className}`}>{children}</div>;
}

function App() {
  const [form, setForm] = useState(initialForm);
  const [submitted, setSubmitted] = useState(false);

  const recommendations = useMemo(() => {
    return benefitPrograms
      .map((program) => scoreProgram(program, form))
      .sort((a, b) => b.score - a.score)
      .slice(0, 3);
  }, [form]);

  const top = recommendations[0];
  const update = (key, value) => setForm((prev) => ({ ...prev, [key]: value }));

  return (
    <main className="page">
      <div className="container">
        <motion.section
          initial={{ opacity: 0, y: 12 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.45 }}
          className="hero"
        >
          <div>
            <div className="hero-pill">
              <Sparkles size={16} /> AI Benefit Navigator for Malaysians
            </div>
            <h1>MyManfaat Agent</h1>
            <p className="hero-text">
              A guided AI agent that interviews users, checks eligibility, recommends suitable aid or support
              programmes, and creates a simple application checklist.
            </p>
            <div className="badge-row">
              <Badge>GovTech</Badge>
              <Badge>FinTech</Badge>
              <Badge>Social Impact</Badge>
              <Badge>Gemini-ready</Badge>
              <Badge>MongoDB-ready</Badge>
            </div>
          </div>

          <Card>
            <p className="eyebrow">Agent workflow</p>
            <div className="workflow">
              {[
                "Collect user context",
                "Search benefit database",
                "Rank eligible programmes",
                "Explain in simple language",
                "Generate checklist + action plan"
              ].map((item, index) => (
                <div key={item} className="workflow-item">
                  <div className="workflow-number">{index + 1}</div>
                  <span>{item}</span>
                </div>
              ))}
            </div>
          </Card>
        </motion.section>

        <section className="tech-strip">
          <div><Cloud size={18} /> Planned Google Cloud / Gemini reasoning</div>
          <div><Database size={18} /> MongoDB-ready benefit database</div>
          <div><ShieldCheck size={18} /> Demo data clearly labelled</div>
        </section>

        <section className="grid">
          <Card>
            <div className="section-title">
              <div className="icon-box"><UserRound size={20} /></div>
              <div>
                <h2>Eligibility Check</h2>
                <p>Answer 6 simple questions.</p>
              </div>
            </div>

            <div className="form">
              <label>
                <span>Age</span>
                <input type="number" value={form.age} onChange={(e) => update("age", e.target.value)} />
              </label>

              <label>
                <span>State</span>
                <div className="input-with-icon">
                  <MapPin size={20} />
                  <input value={form.state} onChange={(e) => update("state", e.target.value)} />
                </div>
              </label>

              <label>
                <span>Employment status</span>
                <select value={form.status} onChange={(e) => update("status", e.target.value)}>
                  <option>Employee</option>
                  <option>Jobseeker</option>
                  <option>Student</option>
                  <option>Business Owner</option>
                  <option>Retiree</option>
                </select>
              </label>

              <label>
                <span>Income category</span>
                <select value={form.income} onChange={(e) => update("income", e.target.value)}>
                  <option>B40</option>
                  <option>M40</option>
                  <option>T20</option>
                </select>
              </label>

              <div>
                <span className="label-text">Main need</span>
                <div className="need-grid">
                  {needs.map(({ value, label, icon: Icon }) => (
                    <button
                      key={value}
                      onClick={() => update("need", value)}
                      className={form.need === value ? "need active" : "need"}
                    >
                      <Icon size={16} /> {label}
                    </button>
                  ))}
                </div>
              </div>

              <label>
                <span>User profile</span>
                <select value={form.role} onChange={(e) => update("role", e.target.value)}>
                  <option>Employee</option>
                  <option>Jobseeker</option>
                  <option>Student</option>
                  <option>Business Owner</option>
                  <option>Parent</option>
                  <option>Retiree</option>
                </select>
              </label>

              <div className="button-row">
                <button className="primary" onClick={() => setSubmitted(true)}>
                  Run Agent <ArrowRight size={16} />
                </button>
                <button
                  className="secondary"
                  onClick={() => {
                    setForm(initialForm);
                    setSubmitted(false);
                  }}
                >
                  <RotateCcw size={16} />
                </button>
              </div>
            </div>
          </Card>

          <div className="results-column">
            <Card>
              <div className="section-title">
                <div className="icon-box"><Search size={20} /></div>
                <div>
                  <h2>Agent Recommendation</h2>
                  <p>
                    {submitted
                      ? "The agent has matched your profile with the best programmes."
                      : "Click Run Agent to generate a recommendation."}
                  </p>
                </div>
              </div>

              {!submitted ? (
                <div className="empty">
                  <Sparkles size={34} />
                  <p>Your personalised benefit plan will appear here.</p>
                </div>
              ) : (
                <motion.div initial={{ opacity: 0, y: 8 }} animate={{ opacity: 1, y: 0 }} className="recommendations">
                  <div className="best-match">
                    <p>Best match</p>
                    <h3>{top.name}</h3>
                    <span>{top.score}% match</span>
                    <p>{top.description}</p>
                  </div>

                  {recommendations.map((item) => (
                    <div key={item.id} className="result-card">
                      <div className="result-header">
                        <div>
                          <h3>{item.name}</h3>
                          <p>{item.category}</p>
                        </div>
                        <strong>{item.score}%</strong>
                      </div>
                      <p>{item.description}</p>
                      <div className="reason-list">
                        {item.reasons.slice(0, 3).map((reason) => (
                          <div key={reason}>
                            <CheckCircle2 size={16} />
                            <span>{reason}</span>
                          </div>
                        ))}
                      </div>
                    </div>
                  ))}
                </motion.div>
              )}
            </Card>

            {submitted && (
              <motion.div initial={{ opacity: 0, y: 8 }} animate={{ opacity: 1, y: 0 }} className="mini-grid">
                <Card>
                  <div className="mini-title"><FileText size={20} /><h3>Document checklist</h3></div>
                  <ul>
                    {top.documents.map((doc) => (
                      <li key={doc}><CheckCircle2 size={16} /> {doc}</li>
                    ))}
                  </ul>
                </Card>

                <Card>
                  <div className="mini-title"><Briefcase size={20} /><h3>Application action plan</h3></div>
                  <ol>
                    {top.steps.map((step, index) => (
                      <li key={step}><span>{index + 1}</span>{step}</li>
                    ))}
                  </ol>
                </Card>
              </motion.div>
            )}
          </div>
        </section>

        <footer>
          <strong>Prototype note:</strong> This demo uses sample benefit data for hackathon demonstration.
          In the full version, programme data should be stored in MongoDB and updated using verified official sources.
        </footer>
      </div>
    </main>
  );
}

createRoot(document.getElementById("root")).render(<App />);
