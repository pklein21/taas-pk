<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Free Accident Case Review — TotalAutoAccident PK</title>
<script src="https://cdn.tailwindcss.com"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/18.2.0/umd/react.production.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/react-dom/18.2.0/umd/react-dom.production.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/7.23.6/babel.min.js"></script>
<style> body { margin:0; } </style>
</head>
<body>
<div id="root"></div>

<script type="text/babel">
const { useState, useMemo } = React;

/* >>> Your deployed Worker URL <<< */
const WORKER_BASE = "https://taas-pk.peter-9fe.workers.dev";

/* ---------- inline icons (lucide-style) ---------- */
function mkIcon(children) {
  return function Icon({ size = 18, color = "currentColor", fill = "none", strokeWidth = 2, className = "", style = {} }) {
    return (
      <svg xmlns="http://www.w3.org/2000/svg" width={size} height={size} viewBox="0 0 24 24"
        fill={fill} stroke={color} strokeWidth={strokeWidth} strokeLinecap="round" strokeLinejoin="round"
        className={className} style={style}>{children}</svg>
    );
  };
}
const Shield = mkIcon(<path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z" />);
const Lock = mkIcon(<><rect x="3" y="11" width="18" height="11" rx="2" /><path d="M7 11V7a5 5 0 0 1 10 0v4" /></>);
const Check = mkIcon(<path d="M20 6 9 17l-5-5" />);
const ChevronLeft = mkIcon(<path d="m15 18-6-6 6-6" />);
const ChevronRight = mkIcon(<path d="m9 18 6-6-6-6" />);
const Star = mkIcon(<path d="M12 2l3.09 6.26L22 9.27l-5 4.87L18.18 21 12 17.77 5.82 21 7 14.14l-5-4.87 6.91-1.01L12 2z" />);
const Loader2 = mkIcon(<path d="M21 12a9 9 0 1 1-6.219-8.56" />);
const Code2 = mkIcon(<><path d="m18 16 4-4-4-4" /><path d="m6 8-4 4 4 4" /><path d="m14.5 4-5 16" /></>);
const RefreshCw = mkIcon(<><path d="M3 12a9 9 0 0 1 9-9 9.75 9.75 0 0 1 6.74 2.74L21 8" /><path d="M21 3v5h-5" /><path d="M21 12a9 9 0 0 1-9 9 9.75 9.75 0 0 1-6.74-2.74L3 16" /><path d="M8 16H3v5" /></>);
const Car = mkIcon(<><path d="M19 17h2c.6 0 1-.4 1-1v-3c0-.9-.7-1.7-1.5-1.9C18.7 10.6 16 10 16 10s-1.3-1.4-2.2-2.3c-.5-.4-1.1-.7-1.8-.7H5c-.6 0-1.1.4-1.4.9l-1.5 2.8A3 3 0 0 0 2 12v4c0 .6.4 1 1 1h2" /><circle cx="7" cy="17" r="2" /><path d="M9 17h6" /><circle cx="17" cy="17" r="2" /></>);
const ScanLine = mkIcon(<><path d="M3 7V5a2 2 0 0 1 2-2h2" /><path d="M17 3h2a2 2 0 0 1 2 2v2" /><path d="M21 17v2a2 2 0 0 1-2 2h-2" /><path d="M7 21H5a2 2 0 0 1-2-2v-2" /><path d="M7 12h10" /></>);
const BadgeCheck = mkIcon(<><path d="M3.85 8.62a4 4 0 0 1 4.78-4.77 4 4 0 0 1 6.74 0 4 4 0 0 1 4.78 4.78 4 4 0 0 1 0 6.74 4 4 0 0 1-4.78 4.78 4 4 0 0 1-6.74 0 4 4 0 0 1-4.78-4.78 4 4 0 0 1 0-6.74z" /><path d="m9 12 2 2 4-4" /></>);
const AlertCircle = mkIcon(<><circle cx="12" cy="12" r="10" /><line x1="12" y1="8" x2="12" y2="12" /><line x1="12" y1="16" x2="12.01" y2="16" /></>);
const Gauge = mkIcon(<><path d="m12 14 4-4" /><path d="M3.34 19a10 10 0 1 1 17.32 0" /></>);
const FileText = mkIcon(<><path d="M15 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V7z" /><path d="M14 2v6h6" /><path d="M16 13H8" /><path d="M16 17H8" /><path d="M10 9H8" /></>);

const C = {
  ink: "#0F2A43", bg: "#F6F4EF", card: "#FFFFFF",
  green: "#15795A", greenDark: "#0F5C44", gold: "#9C6B14",
  goldSoft: "#F3E7CC", tip: "#2C5E8A", tipBg: "#EAF1F7",
  slate: "#5B6B7B", line: "#E7E1D6", softLine: "#F0EBE0",
};

const STEPS = [
  { id: "injured", question: "Were you physically injured in an automobile accident?",
    tip: "The type and severity of your injury has a direct impact on your settlement value.",
    options: [{ label: "Yes", value: "yes", score: 25 }, { label: "No", value: "no", score: 0 }] },
  { id: "fault", question: "Was the accident your fault?",
    tip: "You may still be owed compensation even if you were partially at fault.",
    options: [{ label: "No — the other driver", value: "other", score: 20 },
      { label: "Partially", value: "partial", score: 10 },
      { label: "Still unclear", value: "unclear", score: 8 },
      { label: "Yes — my fault", value: "self", score: 0 }] },
  { id: "timing", question: "When did the accident happen?",
    tip: "Every state has a filing deadline. Acting sooner keeps every option open.",
    options: [{ label: "Within the last week", value: "week", score: 15 },
      { label: "1–6 months ago", value: "1to6", score: 15 },
      { label: "6–24 months ago", value: "6to24", score: 12 },
      { label: "More than 2 years ago", value: "old", score: 2 }] },
  { id: "treatment", question: "Did you receive medical treatment?",
    tip: "Documented medical care is one of the strongest factors in a claim.",
    options: [{ label: "Yes, right away", value: "immediate", score: 20 },
      { label: "Yes, but later", value: "later", score: 12 },
      { label: "Not yet", value: "none", score: 3 }] },
  { id: "impact", question: "Did the injury cause you to miss work or stay overnight in a hospital?",
    tip: "Lost wages and hospital stays add measurable value to a claim.",
    options: [{ label: "Yes — both", value: "both", score: 12 },
      { label: "Missed work only", value: "work", score: 8 },
      { label: "Hospital stay only", value: "hospital", score: 8 },
      { label: "Neither", value: "neither", score: 2 }] },
  { id: "attorney", question: "Are you currently represented by an attorney for this accident?",
    tip: "If you already have representation, an advocate review may not apply.",
    options: [{ label: "No, not yet", value: "no", score: 5 },
      { label: "Yes, already represented", value: "yes", score: 0 }] },
  { id: "offer", question: "Have you received a settlement offer from an insurance company?",
    tip: "Initial offers are often a fraction of what a claim may be worth.",
    options: [{ label: "No offer yet", value: "none", score: 5 },
      { label: "Yes — still deciding", value: "reviewing", score: 4 },
      { label: "Yes — already accepted", value: "accepted", score: 0 }] },
];

const US_STATES = ["AL","AK","AZ","AR","CA","CO","CT","DE","FL","GA","HI","ID","IL","IN","IA","KS","KY","LA","ME","MD","MA","MI","MN","MS","MO","MT","NE","NV","NH","NJ","NM","NY","NC","ND","OH","OK","OR","PA","RI","SC","SD","TN","TX","UT","VT","VA","WA","WV","WI","WY"];

const CONTACT_IDX = STEPS.length;
const MAX_SCORE = STEPS.reduce((s, st) => s + Math.max(...st.options.map(o => o.score)), 0);

function App() {
  const [view, setView] = useState("funnel");
  const [idx, setIdx] = useState(0);
  const [answers, setAnswers] = useState({});
  const [contact, setContact] = useState({ first: "", last: "", phone: "", email: "", zip: "" });

  const [plate, setPlate] = useState("");
  const [plateState, setPlateState] = useState("NY");
  const [vin, setVin] = useState("");
  const [vLoading, setVLoading] = useState(false);
  const [vehicle, setVehicle] = useState(null);
  const [devOpen, setDevOpen] = useState(true);

  const onContact = idx === CONTACT_IDX;
  const step = !onContact ? STEPS[idx] : null;

  const score = useMemo(() => STEPS.reduce((s, st) => {
    const o = st.options.find(x => x.value === answers[st.id]);
    return s + (o ? o.score : 0);
  }, 0), [answers]);
  const strength = Math.round((score / MAX_SCORE) * 100);

  const progress = view === "thanks" ? 100 : view === "boost" ? 92
    : Math.round(((idx + 1) / (STEPS.length + 2)) * 100);

  function choose(v) {
    setAnswers(a => ({ ...a, [step.id]: v }));
    window.setTimeout(() => setIdx(i => i + 1), 200);
  }
  function back() { if (idx > 0) setIdx(i => i - 1); }

  const contactValid =
    contact.first.trim() && contact.last.trim() &&
    contact.phone.trim().length >= 7 && /\S+@\S+\.\S+/.test(contact.email) &&
    contact.zip.trim().length >= 4;

  async function getJSON(path) {
    const r = await fetch(WORKER_BASE + path);
    let body; try { body = await r.json(); } catch { body = await r.text(); }
    return { status: r.status, body };
  }

  async function runLookup(mode) {
    setVLoading(true);
    const out = { mode, input: {}, resolvedVin: "", steps: {}, retrievedAt: new Date().toISOString() };
    try {
      let theVin = vin.trim().toUpperCase();
      if (mode === "plate") {
        out.input = { plate: plate.trim().toUpperCase(), state: plateState };
        const res = await getJSON("/plate/" + plateState + "/" + encodeURIComponent(plate.trim()));
        out.steps.plateDecode = res;
        theVin = (res.body && res.body.data && res.body.data.intro && res.body.data.intro.vin) || "";
      } else {
        out.input = { vin: theVin };
      }
      out.resolvedVin = theVin;
      if (!theVin) throw new Error("No VIN could be resolved from that input.");

      const eps = [["vinDecode", "/vin/" + theVin], ["salesHistory", "/saleshistory/" + theVin], ["marketValue", "/marketvalue/" + theVin]];
      await Promise.all(eps.map(async ([k, p]) => {
        try { out.steps[k] = await getJSON(p); }
        catch (e) { out.steps[k] = { status: "error", error: String(e) }; }
      }));
    } catch (e) {
      out.error = String(e);
    } finally {
      setVehicle(out);
      setVLoading(false);
      setView("thanks");
    }
  }

  function restart() {
    setView("funnel"); setIdx(0); setAnswers({});
    setContact({ first: "", last: "", phone: "", email: "", zip: "" });
    setPlate(""); setVin(""); setVehicle(null);
  }

  const hi = useMemo(() => {
    if (!vehicle) return null;
    const basic = (vehicle.steps.vinDecode && vehicle.steps.vinDecode.body && vehicle.steps.vinDecode.body.data && vehicle.steps.vinDecode.body.data.basic) || {};
    const shArr = vehicle.steps.salesHistory && vehicle.steps.salesHistory.body && vehicle.steps.salesHistory.body.data && vehicle.steps.salesHistory.body.data.sales_history;
    const sh = (shArr && shArr[0] && shArr[0].data) || {};
    return {
      vin: vehicle.resolvedVin,
      ymm: [basic.year, basic.make, basic.model, basic.trim].filter(Boolean).join(" "),
      odometer: sh.odometer_mi ? Number(sh.odometer_mi).toLocaleString() + " mi" : "",
      damage: [sh.primary_damage, sh.secondary_damage].filter(Boolean).join(", "),
      repairCost: (sh.listing_price && sh.listing_price.repair_cost) || "",
      retail: (sh.listing_price && sh.listing_price.retail_value) || "",
      accident: sh.accident_records || "",
      title: sh.title_record || "",
      images: Array.isArray(sh.images) ? sh.images.slice(0, 4) : [],
    };
  }, [vehicle]);

  const workerSet = WORKER_BASE && WORKER_BASE.indexOf("YOUR-WORKER") === -1;

  return (
    <div className="min-h-screen w-full flex flex-col items-center px-4 py-6 sm:py-10"
      style={{ background: C.bg, color: C.ink, fontFamily: "ui-sans-serif, system-ui, sans-serif" }}>

      <header className="w-full max-w-3xl flex items-center justify-between mb-5">
        <div className="flex items-center gap-2">
          <div className="flex items-center justify-center rounded-lg" style={{ width: 34, height: 34, background: C.ink }}>
            <Shield size={18} color="#fff" strokeWidth={2.2} />
          </div>
          <div className="leading-tight">
            <div className="font-semibold tracking-tight" style={{ fontSize: 15 }}>
              TotalAutoAccident <span style={{ color: C.gold }}>PK</span>
            </div>
            <div style={{ fontSize: 11, color: C.slate }}>Accident Advocate Review</div>
          </div>
        </div>
        <div className="hidden sm:flex items-center gap-1.5 rounded-full px-3 py-1"
          style={{ fontSize: 11.5, color: C.slate, background: "#fff", border: "1px solid " + C.line }}>
          <Lock size={12} /> Secure · No obligation
        </div>
      </header>

      {!workerSet && (
        <div className="w-full max-w-3xl mb-3 rounded-lg px-3 py-2 flex items-center gap-2"
          style={{ fontSize: 12, color: C.gold, background: C.goldSoft }}>
          <AlertCircle size={14} /> Set WORKER_BASE near the top of this file to your deployed Worker URL.
        </div>
      )}

      <div className="w-full max-w-3xl mb-4">
        <div className="flex items-center justify-between mb-1.5" style={{ fontSize: 11.5, color: C.slate }}>
          <span>{view === "thanks" ? "Complete" : view === "boost" ? "One last step" : "Step " + Math.min(idx + 1, STEPS.length + 1) + " of " + (STEPS.length + 1)}</span>
          <span>{progress}%</span>
        </div>
        <div className="w-full rounded-full overflow-hidden" style={{ height: 7, background: C.softLine }}>
          <div className="h-full rounded-full transition-all duration-500 ease-out" style={{ width: progress + "%", background: C.green }} />
        </div>
      </div>

      <main className="w-full max-w-3xl grid grid-cols-1 md:grid-cols-[1fr_260px] gap-4">
        <section className="rounded-2xl p-6 sm:p-8"
          style={{ background: C.card, border: "1px solid " + C.line, boxShadow: "0 1px 2px rgba(15,42,67,0.04)" }}>

          {view === "funnel" && step && (
            <div>
              {idx > 0 && (
                <button onClick={back} className="inline-flex items-center gap-1 mb-5" style={{ fontSize: 13, color: C.slate }}>
                  <ChevronLeft size={15} /> Back
                </button>
              )}
              <h1 className="mb-6" style={{ fontFamily: "ui-serif, Georgia, serif", fontSize: 24, lineHeight: 1.25, fontWeight: 600 }}>
                {step.question}
              </h1>
              <div className="flex flex-col gap-2.5">
                {step.options.map(o => {
                  const sel = answers[step.id] === o.value;
                  return (
                    <button key={o.value} onClick={() => choose(o.value)}
                      className="w-full text-left rounded-xl px-4 py-3.5 flex items-center justify-between transition-all duration-150"
                      style={{ border: "1.5px solid " + (sel ? C.green : C.line), background: sel ? "#EAF5F0" : "#fff", fontSize: 15.5, fontWeight: 500 }}
                      onMouseEnter={e => { if (!sel) e.currentTarget.style.borderColor = C.green; }}
                      onMouseLeave={e => { if (!sel) e.currentTarget.style.borderColor = C.line; }}>
                      <span>{o.label}</span>
                      <span className="flex items-center justify-center rounded-full"
                        style={{ width: 22, height: 22, border: "1.5px solid " + (sel ? C.green : C.line), background: sel ? C.green : "transparent" }}>
                        {sel ? <Check size={13} color="#fff" strokeWidth={3} /> : <ChevronRight size={13} color={C.slate} />}
                      </span>
                    </button>
                  );
                })}
              </div>
            </div>
          )}

          {view === "funnel" && onContact && (
            <div>
              <button onClick={back} className="inline-flex items-center gap-1 mb-5" style={{ fontSize: 13, color: C.slate }}>
                <ChevronLeft size={15} /> Back
              </button>
              <h1 className="mb-1" style={{ fontFamily: "ui-serif, Georgia, serif", fontSize: 24, lineHeight: 1.25, fontWeight: 600 }}>
                Where should we send your review?
              </h1>
              <p className="mb-6" style={{ fontSize: 13.5, color: C.slate }}>Free, no obligation. (Mockup — these details are not stored.)</p>
              <div className="grid grid-cols-2 gap-3">
                <Field label="First name" value={contact.first} onChange={v => setContact(c => ({ ...c, first: v }))} />
                <Field label="Last name" value={contact.last} onChange={v => setContact(c => ({ ...c, last: v }))} />
                <Field label="Phone" type="tel" value={contact.phone} onChange={v => setContact(c => ({ ...c, phone: v }))} />
                <Field label="ZIP code" value={contact.zip} onChange={v => setContact(c => ({ ...c, zip: v }))} />
                <div className="col-span-2"><Field label="Email" type="email" value={contact.email} onChange={v => setContact(c => ({ ...c, email: v }))} /></div>
              </div>
              <button onClick={() => setView("boost")} disabled={!contactValid}
                className="w-full mt-6 rounded-xl py-3.5 flex items-center justify-center gap-2 transition-all"
                style={{ background: contactValid ? C.green : "#C7D4CC", color: "#fff", fontSize: 16, fontWeight: 600, cursor: contactValid ? "pointer" : "not-allowed" }}>
                Continue <ChevronRight size={17} />
              </button>
            </div>
          )}

          {view === "boost" && (
            <div>
              <div className="inline-flex items-center gap-1.5 rounded-full px-2.5 py-1 mb-3"
                style={{ fontSize: 11.5, fontWeight: 700, color: C.gold, background: C.goldSoft }}>
                <Star size={12} fill={C.gold} color={C.gold} /> Worth 3–5x more
              </div>
              <h1 className="mb-2" style={{ fontFamily: "ui-serif, Georgia, serif", fontSize: 25, lineHeight: 1.22, fontWeight: 600 }}>
                Your case could be worth <span style={{ color: C.gold }}>3–5x more</span> with a vehicle report.
              </h1>
              <p className="mb-6" style={{ fontSize: 14, color: C.slate, lineHeight: 1.55 }}>
                Add your license plate or VIN and we'll pull the full vehicle record — damage, title, history and value —
                so your advocate can build the strongest possible claim. Most people know their plate; either one works.
              </p>

              {vLoading ? (
                <div className="flex flex-col items-center justify-center py-10 gap-3">
                  <Loader2 size={26} className="animate-spin" color={C.green} />
                  <div style={{ fontSize: 14, color: C.slate }}>Pulling your vehicle records…</div>
                </div>
              ) : (
                <div className="flex flex-col gap-3">
                  <div className="rounded-xl p-4" style={{ border: "1.5px solid " + C.line }}>
                    <div className="flex items-center gap-2 mb-3" style={{ fontSize: 13.5, fontWeight: 700 }}>
                      <ScanLine size={16} color={C.green} /> License plate
                    </div>
                    <div className="grid gap-2" style={{ gridTemplateColumns: "1fr 88px" }}>
                      <input value={plate} onChange={e => setPlate(e.target.value.toUpperCase())} placeholder="ABC1234"
                        className="rounded-lg px-3 py-2.5 outline-none" style={{ border: "1.5px solid " + C.line, fontSize: 15, letterSpacing: 1 }}
                        onFocus={e => e.target.style.borderColor = C.green} onBlur={e => e.target.style.borderColor = C.line} />
                      <select value={plateState} onChange={e => setPlateState(e.target.value)}
                        className="rounded-lg px-2 py-2.5 outline-none" style={{ border: "1.5px solid " + C.line, fontSize: 14, background: "#fff" }}>
                        {US_STATES.map(s => <option key={s} value={s}>{s}</option>)}
                      </select>
                    </div>
                    <button onClick={() => runLookup("plate")} disabled={!plate.trim() || !workerSet}
                      className="w-full mt-3 rounded-lg py-2.5 flex items-center justify-center gap-2"
                      style={{ background: plate.trim() && workerSet ? C.green : "#C7D4CC", color: "#fff", fontSize: 14.5, fontWeight: 600, cursor: plate.trim() && workerSet ? "pointer" : "not-allowed" }}>
                      <Car size={15} /> Unlock my report
                    </button>
                  </div>

                  <div className="flex items-center gap-3" style={{ fontSize: 12, color: C.slate }}>
                    <div className="flex-1" style={{ height: 1, background: C.line }} /> or <div className="flex-1" style={{ height: 1, background: C.line }} />
                  </div>

                  <div className="rounded-xl p-4" style={{ border: "1.5px solid " + C.line }}>
                    <div className="flex items-center gap-2 mb-3" style={{ fontSize: 13.5, fontWeight: 700 }}>
                      <FileText size={16} color={C.green} /> VIN (Vehicle Identification Number)
                    </div>
                    <input value={vin} onChange={e => setVin(e.target.value.toUpperCase())} placeholder="17-character VIN" maxLength={17}
                      className="w-full rounded-lg px-3 py-2.5 outline-none" style={{ border: "1.5px solid " + C.line, fontSize: 15, letterSpacing: 1 }}
                      onFocus={e => e.target.style.borderColor = C.green} onBlur={e => e.target.style.borderColor = C.line} />
                    <button onClick={() => runLookup("vin")} disabled={vin.trim().length < 11 || !workerSet}
                      className="w-full mt-3 rounded-lg py-2.5 flex items-center justify-center gap-2"
                      style={{ background: vin.trim().length >= 11 && workerSet ? C.green : "#C7D4CC", color: "#fff", fontSize: 14.5, fontWeight: 600, cursor: vin.trim().length >= 11 && workerSet ? "pointer" : "not-allowed" }}>
                      <Car size={15} /> Unlock my report
                    </button>
                  </div>

                  <button onClick={() => setView("thanks")} className="mt-1 mx-auto" style={{ fontSize: 12.5, color: C.slate, textDecoration: "underline" }}>
                    Skip for now
                  </button>
                </div>
              )}
            </div>
          )}

          {view === "thanks" && (
            <div>
              <div className="flex items-center gap-2 mb-3">
                <span className="flex items-center justify-center rounded-full" style={{ width: 30, height: 30, background: "#E5F2EC" }}>
                  <BadgeCheck size={18} color={C.greenDark} />
                </span>
                <span className="rounded-full px-2.5 py-1 uppercase tracking-wide" style={{ fontSize: 11, fontWeight: 700, color: C.greenDark, background: "#E5F2EC" }}>
                  Submission received
                </span>
              </div>

              <h1 className="mb-2" style={{ fontFamily: "ui-serif, Georgia, serif", fontSize: 25, lineHeight: 1.25, fontWeight: 600 }}>
                Thank you{contact.first ? ", " + contact.first : ""}.
              </h1>

              {vehicle ? (
                <p className="mb-5" style={{ fontSize: 14, color: C.slate, lineHeight: 1.55 }}>
                  We pulled your vehicle's records — this kind of documentation can meaningfully strengthen a claim.
                  An advocate will review everything below and follow up shortly.
                </p>
              ) : (
                <p className="mb-5" style={{ fontSize: 14, color: C.slate, lineHeight: 1.55 }}>
                  Your review request is in. Adding your plate or VIN later can increase what your case is worth.
                </p>
              )}

              {hi && (hi.ymm || hi.vin) && (
                <div className="rounded-xl p-5 mb-4" style={{ background: "#FBF6EA", border: "1px solid " + C.goldSoft }}>
                  <div className="uppercase tracking-wide mb-2" style={{ fontSize: 11, color: C.gold, fontWeight: 700 }}>Vehicle record found</div>
                  <div style={{ fontSize: 19, fontWeight: 700, fontFamily: "ui-serif, Georgia, serif" }}>{hi.ymm || "Vehicle"}</div>
                  {hi.vin && <div style={{ fontSize: 12.5, color: C.slate, letterSpacing: 1 }}>VIN {hi.vin}</div>}
                  <div className="grid grid-cols-2 gap-x-4 gap-y-2 mt-3">
                    {hi.retail && <Stat icon={Gauge} label="Retail value" value={hi.retail} />}
                    {hi.repairCost && <Stat icon={AlertCircle} label="Est. repair cost" value={hi.repairCost} />}
                    {hi.odometer && <Stat icon={Gauge} label="Odometer" value={hi.odometer} />}
                    {hi.damage && <Stat icon={AlertCircle} label="Damage" value={hi.damage} />}
                    {hi.accident && <Stat icon={FileText} label="Accident records" value={hi.accident} />}
                    {hi.title && <Stat icon={FileText} label="Title record" value={hi.title} />}
                  </div>
                  {hi.images && hi.images.length > 0 && (
                    <div className="flex gap-2 mt-3 overflow-x-auto">
                      {hi.images.map((src, i) => (<img key={i} src={src} alt="" style={{ height: 64, borderRadius: 8, border: "1px solid " + C.line }} />))}
                    </div>
                  )}
                </div>
              )}

              {vehicle && vehicle.error && (
                <div className="rounded-lg px-3 py-2 mb-4 flex items-center gap-2" style={{ fontSize: 12.5, color: C.gold, background: C.goldSoft }}>
                  <AlertCircle size={14} /> {vehicle.error}
                </div>
              )}

              {vehicle && (
                <div className="flex flex-col gap-1.5 mb-4">
                  {Object.entries(vehicle.steps).map(([k, v]) => {
                    const ok = v.status === 200 || (v.body && v.body.status === "success");
                    return (
                      <div key={k} className="flex items-center justify-between rounded-lg px-3 py-2" style={{ fontSize: 12.5, border: "1px solid " + C.line }}>
                        <span style={{ fontWeight: 600 }}>{k}</span>
                        <span className="flex items-center gap-1" style={{ color: ok ? C.greenDark : "#B45454" }}>
                          {ok ? <Check size={13} /> : <AlertCircle size={13} />} {String(v.status)}
                        </span>
                      </div>
                    );
                  })}
                </div>
              )}

              <button className="w-full rounded-xl py-3.5 flex items-center justify-center gap-2"
                style={{ background: C.green, color: "#fff", fontSize: 15.5, fontWeight: 600 }}>
                Talk to an advocate
              </button>

              <div className="flex items-center justify-between mt-4">
                {vehicle && (
                  <button onClick={() => setDevOpen(o => !o)} className="inline-flex items-center gap-1.5" style={{ fontSize: 12, color: C.slate }}>
                    <Code2 size={13} /> {devOpen ? "Hide" : "Show"} raw data + lead payload
                  </button>
                )}
                <button onClick={restart} className="inline-flex items-center gap-1.5 ml-auto" style={{ fontSize: 12, color: C.slate }}>
                  <RefreshCw size={13} /> Restart demo
                </button>
              </div>

              {vehicle && devOpen && (
                <div className="mt-3 flex flex-col gap-3">
                  <DevBlock title="Lead payload to store (plate/VIN lookup only — funnel answers not posted)"
                    obj={{ resolvedVin: vehicle.resolvedVin, input: vehicle.input, retrievedAt: vehicle.retrievedAt, vehicle: vehicle.steps }} />
                </div>
              )}

              <p className="mt-4" style={{ fontSize: 10.5, color: C.slate, lineHeight: 1.5 }}>
                Demo mockup. Vehicle data is retrieved live from VehicleDatabases via your Worker. Figures are illustrative
                and not legal or financial advice.
              </p>
            </div>
          )}
        </section>

        <aside className="flex flex-col gap-4">
          {view === "funnel" && (
            <div className="rounded-2xl p-5" style={{ background: C.tipBg, border: "1px solid #D9E5F0" }}>
              <div className="flex items-center gap-1.5 mb-2" style={{ color: C.tip, fontSize: 12, fontWeight: 700 }}>
                <Star size={13} fill={C.tip} color={C.tip} /> Advocate Tip
              </div>
              <p style={{ fontSize: 13, color: C.ink, lineHeight: 1.5 }}>
                {onContact ? "You're almost done. Your details are only used to deliver your review." : step && step.tip}
              </p>
            </div>
          )}

          {view !== "thanks" && (
            <div className="rounded-2xl p-5" style={{ background: C.card, border: "1px solid " + C.line }}>
              <div className="flex items-center justify-between mb-2">
                <span style={{ fontSize: 12, fontWeight: 600 }}>Case strength</span>
                <span style={{ fontSize: 12, fontWeight: 700, color: C.green }}>{strength}%</span>
              </div>
              <div className="w-full rounded-full overflow-hidden mb-3" style={{ height: 8, background: C.softLine }}>
                <div className="h-full rounded-full transition-all duration-500" style={{ width: strength + "%", background: "linear-gradient(90deg, " + C.green + ", " + C.gold + ")" }} />
              </div>
              <p style={{ fontSize: 11.5, color: C.slate, lineHeight: 1.5 }}>
                {view === "boost" ? "Adding a vehicle report can lift this further." : "Builds as you answer."}
              </p>
            </div>
          )}

          <div className="flex flex-col gap-2 px-1">
            {[{ icon: Lock, t: "256-bit encrypted intake" }, { icon: Shield, t: "No obligation, ever" }, { icon: Check, t: "Free advocate review" }].map((b, i) => {
              const I = b.icon;
              return (
                <div key={i} className="flex items-center gap-2" style={{ fontSize: 12, color: C.slate }}>
                  <I size={13} color={C.green} /> {b.t}
                </div>
              );
            })}
          </div>
        </aside>
      </main>

      <footer className="w-full max-w-3xl mt-6 text-center" style={{ fontSize: 11, color: C.slate }}>
        TotalAutoAccident PK · tech mockup · not affiliated with any law firm
      </footer>
    </div>
  );
}

function Field({ label, value, onChange, type = "text" }) {
  return (
    <label className="flex flex-col gap-1">
      <span style={{ fontSize: 12, color: C.slate, fontWeight: 500 }}>{label}</span>
      <input type={type} value={value} onChange={e => onChange(e.target.value)}
        className="rounded-lg px-3 py-2.5 outline-none" style={{ border: "1.5px solid " + C.line, fontSize: 14.5, background: "#fff" }}
        onFocus={e => e.target.style.borderColor = C.green} onBlur={e => e.target.style.borderColor = C.line} />
    </label>
  );
}

function Stat({ icon: Icon, label, value }) {
  return (
    <div className="flex items-start gap-2">
      <Icon size={14} color={C.gold} style={{ marginTop: 2, flexShrink: 0 }} />
      <div>
        <div style={{ fontSize: 10.5, color: C.slate, textTransform: "uppercase", letterSpacing: 0.4 }}>{label}</div>
        <div style={{ fontSize: 13.5, fontWeight: 600 }}>{value}</div>
      </div>
    </div>
  );
}

function DevBlock({ title, obj }) {
  return (
    <div className="rounded-lg overflow-hidden" style={{ border: "1px solid " + C.line }}>
      <div style={{ fontSize: 11, fontWeight: 700, color: C.slate, padding: "6px 10px", background: "#F7F5F0" }}>{title}</div>
      <pre className="overflow-auto" style={{ fontSize: 10.5, lineHeight: 1.45, margin: 0, padding: 10, maxHeight: 320, background: "#FCFBF8", fontFamily: "ui-monospace, monospace" }}>
        {JSON.stringify(obj, null, 2)}
      </pre>
    </div>
  );
}

ReactDOM.createRoot(document.getElementById("root")).render(<App />);
</script>
</body>
</html>
