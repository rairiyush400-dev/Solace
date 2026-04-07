import { useState, useRef, useEffect, useCallback, useMemo } from "react";

/* ─── Flower SVG petals ─── */
const FlowerSVG = ({ size = 22, opacity = 0.85, hue = 0 }) => (
  <svg width={size} height={size} viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg" style={{ opacity }}>
    {[0,60,120,180,240,300].map((rot, i) => (
      <ellipse key={i} cx="20" cy="20" rx="5" ry="10"
        transform={`rotate(${rot} 20 20) translate(0 -8)`}
        fill={hue === 0 ? "#f9a8c9" : hue === 1 ? "#f472b6" : hue === 2 ? "#fbc8dc" : "#e879a0"}
        opacity="0.9" />
    ))}
    <circle cx="20" cy="20" r="5" fill="#fde8f2" />
  </svg>
);

/* ─── Falling flowers layer ─── */
function FallingFlowers() {
  const flowers = useMemo(() => Array.from({ length: 28 }, (_, i) => ({
    id: i,
    left: Math.random() * 100,
    size: 14 + Math.random() * 18,
    duration: 10 + Math.random() * 18,
    delay: -(Math.random() * 20),
    drift: (Math.random() - 0.5) * 120,
    hue: Math.floor(Math.random() * 4),
    opacity: 0.45 + Math.random() * 0.45,
    rotSpeed: (Math.random() - 0.5) * 720,
  })), []);

  return (
    <div style={{ position: "fixed", inset: 0, pointerEvents: "none", zIndex: 0, overflow: "hidden" }}>
      <style>{`
        @keyframes fall {
          0%   { transform: translateY(-60px) translateX(0px) rotate(0deg); opacity: 0; }
          5%   { opacity: 1; }
          90%  { opacity: 0.8; }
          100% { transform: translateY(105vh) translateX(var(--drift)) rotate(var(--rot)); opacity: 0; }
        }
      `}</style>
      {flowers.map(f => (
        <div key={f.id} style={{
          position: "absolute",
          top: 0,
          left: `${f.left}%`,
          animation: `fall ${f.duration}s ${f.delay}s linear infinite`,
          "--drift": `${f.drift}px`,
          "--rot": `${f.rotSpeed}deg`,
        }}>
          <FlowerSVG size={f.size} opacity={f.opacity} hue={f.hue} />
        </div>
      ))}
    </div>
  );
}

/* ─── Palette ─── */
const PINK = {
  bg: "#fdf0f5",
  bgDeep: "#fce4ef",
  primary: "#c0306a",
  mid: "#e05588",
  soft: "#f4a0c4",
  pale: "#fef5f9",
  border: "#f5c6dc",
  text: "#5a1a35",
  muted: "#b07090",
  card: "rgba(255,255,255,0.72)",
  pill: "#fce8f2",
  pillBorder: "#f0a8cb",
};

/* ─── Global styles ─── */
const G = `
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,400;1,500&family=Jost:wght@300;400;500&display=swap');
*{box-sizing:border-box;margin:0;padding:0;}
body{font-family:'Jost',sans-serif;background:#fdf0f5;}
::-webkit-scrollbar{width:5px;}
::-webkit-scrollbar-thumb{background:#f0b8d0;border-radius:3px;}
@keyframes fadeUp{from{opacity:0;transform:translateY(18px)}to{opacity:1;transform:translateY(0)}}
@keyframes msgIn{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:translateY(0)}}
@keyframes dotBounce{0%,80%,100%{transform:translateY(0);opacity:.35}40%{transform:translateY(-6px);opacity:1}}
@keyframes petalSpin{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}
`;

/* ─── Pill button ─── */
function Pill({ label, selected, onClick }) {
  const [hov, setHov] = useState(false);
  return (
    <button
      onClick={onClick}
      onMouseEnter={() => setHov(true)}
      onMouseLeave={() => setHov(false)}
      style={{
        cursor: "pointer", padding: "9px 20px", borderRadius: 50,
        fontSize: 13.5, fontFamily: "'Jost',sans-serif", fontWeight: selected ? 500 : 400,
        border: `2px solid ${selected ? PINK.primary : hov ? PINK.soft : PINK.border}`,
        background: selected ? PINK.primary : hov ? PINK.pill : PINK.card,
        color: selected ? "#fff" : hov ? PINK.primary : PINK.text,
        transition: "all .18s ease", userSelect: "none", whiteSpace: "normal",
        textAlign: "center", lineHeight: 1.4,
        backdropFilter: "blur(6px)",
        boxShadow: selected ? `0 4px 16px ${PINK.primary}44` : "none",
      }}>
      {label}
    </button>
  );
}

/* ─── Typing dots ─── */
function TypingDots() {
  return (
    <div style={{ display:"flex", gap:6, padding:"14px 18px", background:"rgba(255,255,255,0.85)", borderRadius:18, borderBottomLeftRadius:4, border:`1px solid ${PINK.border}`, backdropFilter:"blur(8px)" }}>
      {[0,160,320].map(d=>(
        <span key={d} style={{ display:"block", width:7, height:7, borderRadius:"50%", background:PINK.soft, animation:`dotBounce 1.2s ${d}ms infinite ease-in-out` }} />
      ))}
    </div>
  );
}

/* ─── Message ─── */
function Message({ msg }) {
  const isAI = msg.role === "ai";
  const html = msg.text.replace(/\*\*(.*?)\*\*/g,"<strong>$1</strong>").replace(/\n\n/g,"<br/><br/>").replace(/\n/g,"<br/>");
  return (
    <div style={{ display:"flex", gap:10, flexDirection:isAI?"row":"row-reverse", animation:"msgIn .35s ease both" }}>
      <div style={{ width:36,height:36,borderRadius:"50%",background:isAI?PINK.bgDeep:"#fff",border:`2px solid ${PINK.border}`,display:"flex",alignItems:"center",justifyContent:"center",fontSize:16,flexShrink:0,marginTop:2 }}>
        {isAI ? "🌸" : "🌿"}
      </div>
      <div style={{ maxWidth:"78%" }}>
        <div style={{
          padding:"13px 18px", borderRadius:18, fontSize:14.5, lineHeight:1.75, fontWeight:300,
          borderBottomLeftRadius:isAI?4:18, borderBottomRightRadius:isAI?18:4,
          background:isAI?"rgba(255,255,255,0.88)":PINK.primary,
          color:isAI?PINK.text:"#fff",
          border:isAI?`1px solid ${PINK.border}`:"none",
          boxShadow:isAI?"0 2px 16px rgba(192,48,106,0.08)":`0 4px 20px ${PINK.primary}55`,
          backdropFilter:"blur(8px)",
          fontFamily:"'Jost',sans-serif",
        }} dangerouslySetInnerHTML={{ __html: html }} />
        <p style={{ fontSize:11,color:PINK.muted,marginTop:5,textAlign:isAI?"left":"right",fontWeight:300 }}>
          {new Date().toLocaleTimeString([],{hour:"2-digit",minute:"2-digit"})}
        </p>
      </div>
    </div>
  );
}

/* ════════════════════════════════
   DATA — detailed intake questions
════════════════════════════════ */
const OCD_DATA = {
  label:"OCD", icon:"🌸",
  title:"Obsessive-Compulsive Disorder",
  tagline:"You are not your thoughts. Let's understand them together.",
  color: PINK.primary,
  sections: [
    {
      heading: "What type of obsessions do you experience?",
      key: "obsType", multi: true,
      opts: ["Intrusive violent thoughts","Fear of harming others","Fear of contamination / germs","Fear of harming yourself","Blasphemous or taboo thoughts","Fear of losing control","Relationship obsessions (ROCD)","Harm OCD","Existential / philosophical loops","Sexual orientation obsessions","Health anxiety loops","Fear of making mistakes","Magical thinking / superstitions","Other unwanted thoughts"],
    },
    {
      heading: "What compulsions or rituals do you perform?",
      key: "compulsions", multi: true,
      opts: ["Checking (locks, stove, switches)","Counting or repeating actions","Mental reviewing / replaying events","Reassurance seeking from others","Googling symptoms or checking facts","Excessive washing or cleaning","Arranging objects in exact order","Avoiding triggers entirely","Confessing / seeking forgiveness","Neutralising thoughts mentally","Tapping or touching rituals","Praying repetitively","Other compulsions"],
    },
    {
      heading: "How severe is the impact on your daily life?",
      key: "severity", multi: false,
      opts: ["Mild — I notice it but mostly function","Moderate — Takes up 1–3 hours daily","Severe — Takes up 3+ hours, affects most things","Debilitating — I struggle to leave home or work"],
    },
    {
      heading: "What triggers your OCD most?",
      key: "triggers", multi: true,
      opts: ["Being alone","Stressful situations","Being around children or vulnerable people","Driving","Watching news / social media","Physical touch or shared spaces","Being in public","Making important decisions","Entering or leaving the house","Having quiet or idle time"],
    },
    {
      heading: "Have you tried anything for it before?",
      key: "tried", multi: true,
      opts: ["Therapy (CBT / ERP)","Medication","Mindfulness or meditation","Self-help books","Nothing yet — this is new","Online communities","Journalling"],
    },
  ],
  descPlaceholder: `Tell me in your own words what a bad OCD day looks like for you. What's the thought or fear that loops the most? What do you do when it hits? Don't hold back — the more specific you are, the more I can help.`,
  system: `You are a deeply compassionate, highly specialised OCD support companion trained in Exposure and Response Prevention (ERP), Acceptance and Commitment Therapy (ACT), and Inference-Based CBT (I-CBT).

You are speaking to someone who has shared detailed personal information about their OCD — their specific obsession types, compulsions, triggers, severity, and a personal description. Use ALL of this information to make every response feel personal and specific to them.

RULES:
- Open by warmly acknowledging their SPECIFIC struggle by name (e.g. "Living with Harm OCD is…" not just "Living with OCD is…")
- Never say "I understand how you feel" — instead SHOW you understand by referencing their exact details
- Explain the OCD cycle as it SPECIFICALLY applies to their described obsessions and compulsions
- Introduce one ERP or ACT concept per session naturally woven into conversation
- Validate the paradox: trying to suppress thoughts makes them louder
- Offer one micro-exercise tailored to their specific compulsion type
- Be warm, human, and gently hopeful — never clinical
- Ask one meaningful follow-up question that deepens understanding
- Keep responses under 220 words
- Never diagnose or replace professional help; recommend a therapist specialising in ERP when appropriate
- Use the person's language and words when possible`
};

const ADHD_DATA = {
  label:"ADHD", icon:"⚡",
  title:"Attention Deficit Hyperactivity Disorder",
  tagline:"Your brain works differently — and that's a feature, not a flaw.",
  color: "#7c3aed",
  sections: [
    {
      heading: "Which type best describes your experience?",
      key: "adhdType", multi: false,
      opts: ["Primarily inattentive (zoning out, losing things)","Primarily hyperactive / impulsive","Combined type (both)","Not sure — I just know something feels different"],
    },
    {
      heading: "What are your biggest day-to-day challenges?",
      key: "challenges", multi: true,
      opts: ["Starting tasks (task paralysis)","Finishing what I started","Keeping track of time","Losing things constantly","Forgetting conversations or instructions","Hyperfocusing on the 'wrong' thing","Interrupting people / blurting things out","Restlessness — can't sit still","Emotional dysregulation / mood swings","Sensitivity to criticism (RSD)","Procrastinating until the last minute","Difficulty sleeping","Managing money / bills","Maintaining relationships"],
    },
    {
      heading: "How does it affect your life most?",
      key: "lifeArea", multi: true,
      opts: ["Work or career performance","Academic studies","Romantic relationships","Friendships and social life","Parenting","Self-esteem and confidence","Daily routines and self-care","Finances","Physical health","Creative projects / hobbies"],
    },
    {
      heading: "When is it hardest to manage?",
      key: "hardest", multi: true,
      opts: ["When I have no external deadline","When tasks feel boring or pointless","In meetings or long conversations","When I'm overstimulated","When I'm tired or hungry","When I'm stressed","When there are too many choices","When I have to switch tasks","When the environment is messy","In the mornings"],
    },
    {
      heading: "What emotions come up most around your ADHD?",
      key: "emotions", multi: true,
      opts: ["Shame and guilt","Frustration with myself","Anxiety about forgetting things","Fear of failure","Feeling misunderstood","Loneliness","Anger","Grief (for lost time or potential)","Hope — I want to get better","Overwhelm"],
    },
    {
      heading: "Have you tried any strategies?",
      key: "tried", multi: true,
      opts: ["Medication (stimulants)","Medication (non-stimulants)","CBT or coaching","Body doubling","Timers / time-blocking","To-do apps or planners","Mindfulness","Exercise","Dietary changes","Nothing formal yet"],
    },
  ],
  descPlaceholder: `Describe a recent moment where ADHD really got in the way for you. What happened? What were you feeling? What did you wish you could do differently? Be as specific as you can — the more real details you share, the more personalised and useful my support can be.`,
  system: `You are a deeply compassionate, highly specialised ADHD support companion trained in CBT adapted for ADHD, executive function coaching, and Rejection Sensitive Dysphoria (RSD) awareness.

You are speaking to someone who has shared detailed personal information about their ADHD — their subtype, challenges, affected life areas, emotional experience, and a personal description. Use ALL of this to make every response feel completely personal and specific.

RULES:
- Start by naming their SPECIFIC challenges (e.g. "Task paralysis combined with time blindness is…" — not just "ADHD can be hard")
- Acknowledge the emotional weight FIRST — shame, frustration, grief are real and valid
- Validate that this is neurological, not laziness or a character flaw
- Offer ONE concrete, immediately actionable strategy specific to their described challenge — specificity is kindness
- Explain the WHY behind their experience (e.g. dopamine deficit, working memory issues)
- Be energetic but gentle — match ADHD brains that need engagement
- Ask one meaningful follow-up question that shows you truly heard them
- Keep responses under 220 words
- Never shame or suggest they "just need to try harder"
- Recommend professional ADHD coaching or psychiatry where appropriate`
};

/* ════════════════
   LANDING SCREEN
════════════════ */
function Landing({ onSelect }) {
  return (
    <div style={{ minHeight:"100vh", background:PINK.bg, fontFamily:"'Jost',sans-serif", display:"flex", flexDirection:"column", position:"relative", zIndex:1 }}>
      <div style={{ display:"flex", justifyContent:"space-between", alignItems:"center", padding:"26px 44px", position:"relative", zIndex:2 }}>
        <span style={{ fontFamily:"'Cormorant Garamond',serif", fontSize:24, fontWeight:500, color:PINK.text, letterSpacing:-0.5 }}>
          Sol<span style={{color:PINK.primary}}>ace</span>
        </span>
        <span style={{ fontSize:12, color:PINK.muted, fontStyle:"italic" }}>Private & confidential 🌸</span>
      </div>

      <div style={{ flex:1, display:"flex", flexDirection:"column", alignItems:"center", justifyContent:"center", padding:"32px 24px 60px", position:"relative", zIndex:2, textAlign:"center" }}>
        <p style={{ fontSize:11, letterSpacing:3.5, textTransform:"uppercase", color:PINK.soft, fontWeight:500, marginBottom:22, animation:"fadeUp .5s ease both" }}>
          Mental Wellness Companion
        </p>
        <h1 style={{ fontFamily:"'Cormorant Garamond',serif", fontSize:"clamp(44px,7vw,80px)", fontWeight:400, lineHeight:1.06, letterSpacing:-2, color:PINK.text, marginBottom:20, animation:"fadeUp .65s ease both" }}>
          A gentle place<br /><em style={{color:PINK.primary, fontStyle:"italic"}}>to begin healing.</em>
        </h1>
        <p style={{ fontSize:16, color:PINK.muted, lineHeight:1.75, maxWidth:420, fontWeight:300, marginBottom:56, animation:"fadeUp .8s ease both" }}>
          Personalised, thoughtful support for OCD and ADHD — because your experience is unlike anyone else's.
        </p>

        <p style={{ fontSize:11.5, letterSpacing:2.5, textTransform:"uppercase", color:PINK.soft, fontWeight:400, marginBottom:22, animation:"fadeUp .9s ease both" }}>
          What would you like support with?
        </p>

        <div style={{ display:"grid", gridTemplateColumns:"1fr 1fr", gap:18, maxWidth:600, width:"100%", animation:"fadeUp 1s ease both" }}>
          {[OCD_DATA, ADHD_DATA].map((c,i) => <CondCard key={i} cond={c} onSelect={onSelect} />)}
        </div>

        <p style={{ marginTop:48, fontSize:12, color:PINK.soft, fontStyle:"italic", animation:"fadeUp 1.1s ease both" }}>
          Not a substitute for professional care. Please also speak with a licensed therapist.
        </p>
      </div>
    </div>
  );
}

function CondCard({ cond, onSelect }) {
  const [hov, setHov] = useState(false);
  const isAdhd = cond.label === "ADHD";
  return (
    <div onClick={() => onSelect(cond.label.toLowerCase())}
      onMouseEnter={() => setHov(true)} onMouseLeave={() => setHov(false)}
      style={{
        cursor:"pointer", borderRadius:24, padding:"30px 26px 26px", textAlign:"left",
        background:hov?"rgba(255,255,255,0.95)":PINK.card,
        border:`2px solid ${hov?(isAdhd?"#c4b5fd":PINK.soft):PINK.border}`,
        backdropFilter:"blur(10px)", WebkitBackdropFilter:"blur(10px)",
        transition:"transform .22s ease, box-shadow .22s ease, border-color .22s ease",
        transform:hov?"translateY(-6px)":"translateY(0)",
        boxShadow:hov?`0 20px 56px ${isAdhd?"rgba(124,58,237,.18)":PINK.primary+"33"}`:"0 4px 16px rgba(192,48,106,0.07)",
        position:"relative",
      }}>
      <div style={{ fontSize:26, marginBottom:14 }}>{cond.icon}</div>
      <p style={{ fontSize:10.5, letterSpacing:2.5, textTransform:"uppercase", color:isAdhd?"#7c3aed":PINK.primary, fontWeight:500, marginBottom:8 }}>{cond.label}</p>
      <h2 style={{ fontFamily:"'Cormorant Garamond',serif", fontSize:20, fontWeight:500, lineHeight:1.25, marginBottom:10, color:PINK.text }}>{cond.title}</h2>
      <p style={{ fontSize:12.5, color:PINK.muted, lineHeight:1.6, fontWeight:300, fontStyle:"italic" }}>{cond.tagline}</p>
      <div style={{ marginTop:18, fontSize:12, color:PINK.muted, display:"flex", alignItems:"center", gap:5 }}>
        <span>{cond.sections.length} detailed questions</span>
        <span style={{ transition:"transform .2s", transform:hov?"translateX(4px)":"translateX(0)", color:isAdhd?"#7c3aed":PINK.primary }}>→</span>
      </div>
    </div>
  );
}

/* ══════════════
   INTAKE SCREEN
══════════════ */
function Intake({ condId, onBack, onStart }) {
  const c = condId === "ocd" ? OCD_DATA : ADHD_DATA;
  const isAdhd = condId === "adhd";
  const accentColor = isAdhd ? "#7c3aed" : PINK.primary;

  const [answers, setAnswers] = useState({});
  const [desc, setDesc] = useState("");
  const [loading, setLoading] = useState(false);

  function toggle(key, val, multi) {
    setAnswers(prev => {
      if (!multi) return { ...prev, [key]: val };
      const cur = prev[key] || [];
      return { ...prev, [key]: cur.includes(val) ? cur.filter(v=>v!==val) : [...cur, val] };
    });
  }

  const allAnswered = c.sections.every(s => {
    const a = answers[s.key];
    return s.multi ? (a && a.length > 0) : !!a;
  });
  const canSubmit = allAnswered && desc.trim().length > 20 && !loading;

  async function handleStart() {
    setLoading(true);
    await onStart({ answers, desc });
    setLoading(false);
  }

  return (
    <div style={{ minHeight:"100vh", background:PINK.bg, fontFamily:"'Jost',sans-serif", display:"flex", flexDirection:"column", position:"relative", zIndex:1 }}>
      {/* Nav */}
      <div style={{ display:"flex", alignItems:"center", gap:14, padding:"20px 36px", borderBottom:`1px solid ${PINK.border}`, background:"rgba(253,240,245,0.9)", backdropFilter:"blur(10px)", position:"sticky", top:0, zIndex:50 }}>
        <button onClick={onBack} style={{ background:"rgba(255,255,255,0.8)", border:`1.5px solid ${PINK.border}`, borderRadius:50, padding:"7px 18px", fontSize:13, cursor:"pointer", fontFamily:"'Jost',sans-serif", color:PINK.text }}>← Back</button>
        <span style={{ fontSize:11, letterSpacing:2, textTransform:"uppercase", fontWeight:500, padding:"5px 14px", borderRadius:50, background:accentColor, color:"#fff" }}>
          {c.label} Support
        </span>
        <span style={{ fontSize:12.5, color:PINK.muted, fontStyle:"italic" }}>{c.tagline}</span>
      </div>

      <div style={{ maxWidth:700, margin:"0 auto", width:"100%", padding:"40px 28px 80px", animation:"fadeUp .4s ease" }}>
        <div style={{ textAlign:"center", marginBottom:44 }}>
          <div style={{ fontSize:36, marginBottom:12 }}>{c.icon}</div>
          <h1 style={{ fontFamily:"'Cormorant Garamond',serif", fontSize:"clamp(28px,5vw,44px)", fontWeight:500, lineHeight:1.15, color:PINK.text, marginBottom:10 }}>
            Help us understand <em style={{color:accentColor}}>your experience</em>
          </h1>
          <p style={{ fontSize:15, color:PINK.muted, fontWeight:300, lineHeight:1.7, maxWidth:500, margin:"0 auto" }}>
            The more you share, the more personalised and genuinely useful your support will be. Take your time.
          </p>
        </div>

        {c.sections.map((sec, si) => (
          <div key={si} style={{ marginBottom:36, background:PINK.card, borderRadius:20, padding:"24px 24px 20px", border:`1.5px solid ${PINK.border}`, backdropFilter:"blur(8px)", animation:`fadeUp ${.3+si*.08}s ease both` }}>
            <p style={{ fontSize:12, letterSpacing:1.5, textTransform:"uppercase", fontWeight:500, color:accentColor, marginBottom:6 }}>
              {si+1} of {c.sections.length}
            </p>
            <p style={{ fontSize:16, fontFamily:"'Cormorant Garamond',serif", fontWeight:500, color:PINK.text, lineHeight:1.45, marginBottom:16 }}>{sec.heading}</p>
            {sec.multi && <p style={{ fontSize:12, color:PINK.muted, marginBottom:12, fontStyle:"italic" }}>Select all that apply</p>}
            <div style={{ display:"flex", flexWrap:"wrap", gap:9 }}>
              {sec.opts.map(opt => {
                const cur = answers[sec.key];
                const sel = sec.multi ? (cur||[]).includes(opt) : cur===opt;
                return (
                  <Pill key={opt} label={opt} selected={sel}
                    onClick={() => toggle(sec.key, opt, sec.multi)} />
                );
              })}
            </div>
          </div>
        ))}

        {/* Free text */}
        <div style={{ background:PINK.card, borderRadius:20, padding:"24px", border:`1.5px solid ${PINK.border}`, backdropFilter:"blur(8px)", marginBottom:24, animation:`fadeUp ${.3+c.sections.length*.08}s ease both` }}>
          <p style={{ fontSize:12, letterSpacing:1.5, textTransform:"uppercase", fontWeight:500, color:accentColor, marginBottom:6 }}>
            {c.sections.length+1} of {c.sections.length+1}
          </p>
          <p style={{ fontSize:16, fontFamily:"'Cormorant Garamond',serif", fontWeight:500, color:PINK.text, marginBottom:16, lineHeight:1.45 }}>
            In your own words — describe your experience
          </p>
          <div style={{ position:"relative" }}>
            <textarea
              value={desc}
              onChange={e => setDesc(e.target.value)}
              placeholder={c.descPlaceholder}
              maxLength={1400}
              style={{
                width:"100%", minHeight:160, padding:"16px 18px 40px",
                borderRadius:14, fontFamily:"'Jost',sans-serif", fontSize:14.5,
                fontWeight:300, color:PINK.text, lineHeight:1.7, resize:"vertical", outline:"none",
                border:`2px solid ${desc.length>20?accentColor:PINK.border}`,
                background:"rgba(255,255,255,0.7)",
                transition:"border-color .2s, box-shadow .2s",
                boxShadow:desc.length>20?`0 0 0 4px ${accentColor}18`:"none",
              }}
            />
            <span style={{ position:"absolute", bottom:12, right:14, fontSize:11, color:PINK.muted }}>{desc.length}/1400</span>
          </div>
        </div>

        <button onClick={handleStart} disabled={!canSubmit}
          style={{
            width:"100%", padding:"18px 32px", borderRadius:16, border:"none",
            cursor:canSubmit?"pointer":"not-allowed",
            fontFamily:"'Cormorant Garamond',serif", fontSize:20, fontStyle:"italic", fontWeight:500, color:"#fff",
            background:canSubmit?`linear-gradient(135deg, ${accentColor}, ${isAdhd?"#a855f7":PINK.mid})`:"#ddd",
            boxShadow:canSubmit?`0 10px 32px ${accentColor}44`:"none",
            transition:"all .2s", opacity:loading?.75:1,
          }}
          onMouseEnter={e=>{if(canSubmit)e.currentTarget.style.transform="translateY(-2px)"}}
          onMouseLeave={e=>{e.currentTarget.style.transform="translateY(0)"}}>
          {loading ? "Preparing your personalised session…" : "Begin my session 🌸"}
        </button>

        {!allAnswered && <p style={{ textAlign:"center", fontSize:12.5, color:PINK.muted, marginTop:12, fontStyle:"italic" }}>
          Please answer all questions above to continue
        </p>}
      </div>
    </div>
  );
}

/* ═══════════════
   THERAPY SCREEN
═══════════════ */
function Therapy({ condId, profile, onNewSession }) {
  const c = condId === "ocd" ? OCD_DATA : ADHD_DATA;
  const isAdhd = condId === "adhd";
  const accentColor = isAdhd ? "#7c3aed" : PINK.primary;

  const [messages, setMessages] = useState([]);
  const [input, setInput] = useState("");
  const [typing, setTyping] = useState(false);
  const histRef = useRef([]);
  const bottomRef = useRef(null);
  const inputRef = useRef(null);
  const didInit = useRef(false);

  useEffect(() => { bottomRef.current?.scrollIntoView({ behavior:"smooth" }); }, [messages, typing]);

  const callAPI = useCallback(async (history) => {
    const res = await fetch("https://api.anthropic.com/v1/messages", {
      method:"POST",
      headers:{"Content-Type":"application/json"},
      body:JSON.stringify({
        model:"claude-sonnet-4-20250514",
        max_tokens:1000,
        system:c.system,
        messages:history,
      }),
    });
    if (!res.ok) throw new Error(res.status);
    const d = await res.json();
    return d.content?.[0]?.text || "I'm here with you. Can you tell me more?";
  }, [c.system]);

  useEffect(() => {
    if (didInit.current) return;
    didInit.current = true;

    // Build a rich first message from profile
    const { answers, desc } = profile;
    const lines = [`Condition: ${c.label}`];
    c.sections.forEach(sec => {
      const a = answers[sec.key];
      if (a) {
        const val = Array.isArray(a) ? a.join(", ") : a;
        lines.push(`${sec.heading}: ${val}`);
      }
    });
    lines.push(`\nPersonal description from the user:\n"${desc}"`);

    const firstMsg = lines.join("\n");
    const history = [{ role:"user", content:firstMsg }];
    histRef.current = history;

    setTyping(true);
    callAPI(history).then(reply => {
      histRef.current = [...history, { role:"assistant", content:reply }];
      setMessages([{ role:"ai", text:reply }]);
      setTyping(false);
    }).catch(() => {
      const fb = "I'm here with you. There was a small hiccup — could you tell me a bit about what's been on your mind lately?";
      histRef.current = [...history, { role:"assistant", content:fb }];
      setMessages([{ role:"ai", text:fb }]);
      setTyping(false);
    });
  }, [callAPI, c, profile]);

  async function send() {
    const text = input.trim();
    if (!text || typing) return;
    setInput("");
    if (inputRef.current) { inputRef.current.style.height="auto"; }
    const newHist = [...histRef.current, { role:"user", content:text }];
    histRef.current = newHist;
    setMessages(prev => [...prev, { role:"user", text }]);
    setTyping(true);
    try {
      const reply = await callAPI(newHist);
      histRef.current = [...newHist, { role:"assistant", content:reply }];
      setMessages(prev => [...prev, { role:"ai", text:reply }]);
    } catch {
      setMessages(prev => [...prev, { role:"ai", text:"I'm still here — there was a brief connection issue. What were you sharing?" }]);
    }
    setTyping(false);
  }

  // Summary of what user shared
  const summaryParts = [];
  c.sections.slice(0,2).forEach(sec => {
    const a = profile.answers[sec.key];
    if (a) summaryParts.push(Array.isArray(a) ? a.slice(0,2).join(" · ") : a);
  });

  return (
    <div style={{ height:"100vh", background:PINK.bg, fontFamily:"'Jost',sans-serif", display:"flex", flexDirection:"column", position:"relative", zIndex:1 }}>
      {/* Nav */}
      <div style={{ display:"flex", alignItems:"center", justifyContent:"space-between", padding:"14px 32px", borderBottom:`1px solid ${PINK.border}`, background:"rgba(253,240,245,0.92)", backdropFilter:"blur(12px)", flexShrink:0, zIndex:50 }}>
        <span style={{ fontFamily:"'Cormorant Garamond',serif", fontSize:18, fontWeight:500, color:accentColor }}>
          {c.icon} Solace · {c.label}
        </span>
        <div style={{ display:"flex", alignItems:"center", gap:7, fontSize:12.5, color:PINK.muted }}>
          <span style={{ width:7, height:7, borderRadius:"50%", background:PINK.soft, display:"inline-block" }} />
          Session active
        </div>
        <button onClick={onNewSession}
          style={{ background:"rgba(255,255,255,0.7)", border:`1.5px solid ${PINK.border}`, borderRadius:50, padding:"6px 15px", fontSize:12, cursor:"pointer", fontFamily:"'Jost',sans-serif", color:PINK.text }}>
          New session
        </button>
      </div>

      {/* Context strip */}
      <div style={{ background:"rgba(252,228,239,0.6)", padding:"10px 24px", display:"flex", gap:10, alignItems:"center", flexShrink:0, borderBottom:`1px solid ${PINK.border}`, backdropFilter:"blur(6px)" }}>
        <span style={{ fontSize:13 }}>🌸</span>
        <p style={{ fontSize:12.5, color:PINK.muted, fontStyle:"italic", fontWeight:300 }}>
          {summaryParts.join(" · ")} · Personalised session
        </p>
      </div>

      {/* Messages */}
      <div style={{ flex:1, overflowY:"auto", padding:"24px 20px", display:"flex", flexDirection:"column", gap:20, maxWidth:760, margin:"0 auto", width:"100%" }}>
        {messages.map((msg,i) => <Message key={i} msg={msg} />)}
        {typing && (
          <div style={{ display:"flex", gap:10, alignItems:"center" }}>
            <div style={{ width:36, height:36, borderRadius:"50%", background:PINK.bgDeep, border:`2px solid ${PINK.border}`, display:"flex", alignItems:"center", justifyContent:"center", fontSize:16, flexShrink:0 }}>🌸</div>
            <TypingDots />
          </div>
        )}
        <div ref={bottomRef} />
      </div>

      {/* Input */}
      <div style={{ flexShrink:0, maxWidth:760, margin:"0 auto", width:"100%", padding:"0 20px 20px" }}>
        <div style={{
          display:"flex", gap:10, alignItems:"flex-end", padding:"12px 16px",
          background:"rgba(255,255,255,0.85)", borderRadius:20,
          border:`2px solid ${input?accentColor:PINK.border}`,
          backdropFilter:"blur(10px)", WebkitBackdropFilter:"blur(10px)",
          boxShadow:input?`0 4px 24px ${accentColor}22`:"0 4px 20px rgba(192,48,106,0.07)",
          transition:"border-color .2s, box-shadow .2s",
        }}>
          <textarea ref={inputRef} value={input}
            onChange={e => { setInput(e.target.value); e.target.style.height="auto"; e.target.style.height=Math.min(e.target.scrollHeight,120)+"px"; }}
            onKeyDown={e => { if(e.key==="Enter"&&!e.shiftKey){e.preventDefault();send();} }}
            placeholder="Share what's on your mind…"
            rows={1}
            style={{ flex:1, border:"none", outline:"none", fontFamily:"'Jost',sans-serif", fontSize:14.5, fontWeight:300, color:PINK.text, background:"transparent", resize:"none", maxHeight:120, lineHeight:1.6, padding:0 }}
          />
          <button onClick={send} disabled={!input.trim()||typing}
            style={{
              width:38, height:38, borderRadius:"50%", border:"none",
              background:input.trim()&&!typing?accentColor:"#e8d0dc",
              color:"#fff", fontSize:17, cursor:input.trim()&&!typing?"pointer":"not-allowed",
              display:"flex", alignItems:"center", justifyContent:"center", flexShrink:0,
              transition:"background .15s, transform .15s",
            }}
            onMouseEnter={e=>{if(input.trim()&&!typing)e.currentTarget.style.transform="scale(1.1)"}}
            onMouseLeave={e=>{e.currentTarget.style.transform="scale(1)"}}>
            ↑
          </button>
        </div>
        <p style={{ textAlign:"center", fontSize:11, color:PINK.soft, fontStyle:"italic", marginTop:10 }}>
          Not a substitute for therapy · If in crisis, please contact a helpline 🌸
        </p>
      </div>
    </div>
  );
}

/* ══════════
   ROOT APP
══════════ */
export default function App() {
  const [screen, setScreen] = useState("landing");
  const [condId, setCondId] = useState(null);
  const [profile, setProfile] = useState(null);

  function selectCond(id) { setCondId(id); setScreen("intake"); }
  function goBack() { setScreen("landing"); }
  async function startSession(p) { setProfile(p); setScreen("therapy"); }
  function newSession() { setCondId(null); setProfile(null); setScreen("landing"); }

  return (
    <>
      <style>{G}</style>
      <FallingFlowers />
      <div style={{ position:"relative", zIndex:1 }}>
        {screen === "landing"  && <Landing onSelect={selectCond} />}
        {screen === "intake"   && <Intake condId={condId} onBack={goBack} onStart={startSession} />}
        {screen === "therapy"  && <Therapy condId={condId} profile={profile} onNewSession={newSession} />}
      </div>
    </>
  );
}
