import { useState } from 'react'

const PHONE = '+966 68 667 886'
const PHONE_TEL = 'tel:+96668667886'
const WA_LINK = 'https://wa.me/96668667886?text=Hi%20Recovery%20Point%2C%20I%20need%20a%20tow.%20My%20location%3A%20'

function Logo({ size = 42 }) {
  return (
    <svg width={size} height={size} viewBox="0 0 42 42" fill="none">
      <circle cx="21" cy="21" r="20" stroke="#FFC72C" strokeWidth="1.5" />
      <path d="M12 26 L15 17 L20 17 L20 14 L26 14 L29 20 L30 26 Z" fill="none" stroke="#FFC72C" strokeWidth="1.6" strokeLinejoin="round" />
      <circle cx="16.5" cy="27.5" r="2.4" fill="#15171C" stroke="#FFC72C" strokeWidth="1.4" />
      <circle cx="26.5" cy="27.5" r="2.4" fill="#15171C" stroke="#FFC72C" strokeWidth="1.4" />
      <path d="M23 8 L23 13 M20.5 10.5 L25.5 10.5" stroke="#FFC72C" strokeWidth="1.4" strokeLinecap="round" />
    </svg>
  )
}

function Eyebrow({ children }) {
  return (
    <span className="eyebrow">
      <span className="eyebrow-dot" />
      {children}
    </span>
  )
}

function Header({ menuOpen, setMenuOpen }) {
  return (
    <header>
      <div className="wrap nav">
        <div className="brand">
          <Logo />
          <div className="brand-word">RECOVERY <span>POINT</span></div>
        </div>
        <nav className={`nav-links ${menuOpen ? 'open' : ''}`}>
          <a href="#services" onClick={() => setMenuOpen(false)}>Services</a>
          <a href="#fleet" onClick={() => setMenuOpen(false)}>Fleet</a>
          <a href="#how" onClick={() => setMenuOpen(false)}>How It Works</a>
          <a href="#about" onClick={() => setMenuOpen(false)}>About</a>
          <a href="#contact" onClick={() => setMenuOpen(false)}>Contact</a>
        </nav>
        <div className="nav-actions">
          <div className="nav-phone">
            <small>24/7 Dispatch</small>
            <strong>{PHONE}</strong>
          </div>
          <a className="btn btn-call" href={PHONE_TEL}>Call Now</a>
          <button className="menu-toggle" aria-label="Menu" onClick={() => setMenuOpen(!menuOpen)}>
            {menuOpen ? '✕' : '☰'}
          </button>
        </div>
      </div>
    </header>
  )
}

function HeroArt() {
  return (
    <div className="hero-art">
      <div className="hero-badge"><span className="pulse-dot" /> LIVE — DISPATCH READY</div>
      <svg viewBox="0 0 560 380" width="100%">
        <defs>
          <linearGradient id="sky" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0%" stopColor="#272B36" />
            <stop offset="100%" stopColor="#15171C" />
          </linearGradient>
        </defs>
        <rect x="0" y="0" width="560" height="380" rx="10" fill="url(#sky)" />
        <rect x="0" y="300" width="560" height="80" fill="#1E212A" />
        <line x1="0" y1="300" x2="560" y2="300" stroke="#3A3E49" strokeWidth="2" />
        <line x1="20" y1="330" x2="540" y2="330" stroke="#FFC72C" strokeWidth="4" strokeDasharray="26 20" opacity="0.7" />
        <g transform="translate(60,190)">
          <rect x="0" y="30" width="100" height="55" rx="4" fill="#272B36" stroke="#8891A3" strokeWidth="1.5" />
          <path d="M100 30 L140 30 L160 60 L160 85 L100 85 Z" fill="#272B36" stroke="#8891A3" strokeWidth="1.5" />
          <rect x="108" y="38" width="34" height="20" rx="2" fill="#15171C" stroke="#FFC72C" strokeWidth="1.3" />
          <rect x="0" y="10" width="24" height="24" fill="#FFC72C" />
          <circle cx="30" cy="90" r="15" fill="#15171C" stroke="#8891A3" strokeWidth="2" />
          <circle cx="30" cy="90" r="5" fill="#8891A3" />
          <circle cx="135" cy="90" r="15" fill="#15171C" stroke="#8891A3" strokeWidth="2" />
          <circle cx="135" cy="90" r="5" fill="#8891A3" />
          <path d="M160 45 L210 20" stroke="#8891A3" strokeWidth="2" />
          <circle cx="210" cy="20" r="3" fill="#FFC72C" />
        </g>
        <path d="M270 210 L330 250" stroke="#F2A93B" strokeWidth="2" strokeDasharray="4 4" />
        <g transform="translate(320,230)">
          <path d="M0 40 Q4 10 40 8 L110 8 Q140 8 150 40 L150 55 L0 55 Z" fill="#1E212A" stroke="#E14A2E" strokeWidth="1.6" />
          <rect x="45" y="12" width="55" height="20" rx="3" fill="#15171C" stroke="#E14A2E" strokeWidth="1.2" />
          <circle cx="30" cy="55" r="13" fill="#15171C" stroke="#8891A3" strokeWidth="2" />
          <circle cx="118" cy="55" r="13" fill="#15171C" stroke="#8891A3" strokeWidth="2" />
        </g>
        <circle cx="72" cy="188" r="3" fill="#FFC72C">
          <animate attributeName="opacity" values="1;0.2;1" dur="1s" repeatCount="indefinite" />
        </circle>
      </svg>
    </div>
  )
}

function Hero() {
  return (
    <section className="hero">
      <div className="wrap">
        <div className="hero-grid">
          <div>
            <Eyebrow>24/7 Emergency Vehicle Recovery</Eyebrow>
            <h1>Stuck on the road?<br />We're <em>already</em> on our way.</h1>
            <p className="lede">Recovery Point connects stranded drivers with pickup trucks and tow trucks nearby — for accidents, breakdowns, and cars stuck far from town. One call, one truck, on the move.</p>
            <div className="hero-actions">
              <a className="btn btn-call" href={PHONE_TEL}>Call {PHONE}</a>
              <a className="btn btn-wa" href={WA_LINK} target="_blank" rel="noopener">WhatsApp Us</a>
            </div>
            <div className="hero-stats">
              <div><strong>24/7</strong><span>Dispatch Line</span></div>
              <div><strong>3</strong><span>Truck Classes</span></div>
              <div><strong>&lt;30min</strong><span>Avg. Response*</span></div>
            </div>
          </div>
          <HeroArt />
        </div>
      </div>
    </section>
  )
}

function Ticker() {
  const items = [
    'UNIT-01 FLATBED — AVAILABLE',
    'UNIT-02 WHEEL-LIFT — EN ROUTE, ETA 14 MIN',
    'UNIT-03 HEAVY PICKUP — AVAILABLE',
    'DISPATCH LINE OPEN 24/7',
    'COVERING CITY & SURROUNDING ROUTES',
  ]
  const doubled = [...items, ...items]
  return (
    <div className="ticker">
      <div className="ticker-track">
        {doubled.map((item, i) => (
          <span key={i}>
            <span className="ticker-dot">●</span> {item}{'  '}
          </span>
        ))}
      </div>
    </div>
  )
}

const SERVICES = [
  { title: 'Accident Recovery', desc: 'Fast, careful towing for vehicles damaged in a collision — flatbed loading to avoid further damage.', icon: 'M6 26 L10 16 H24 L30 26 M6 26 H30 M6 26 V30 H30 V26' },
  { title: 'Breakdown Towing', desc: 'Engine trouble, flat tires, dead battery — we\'ll get you and your car off the road safely.', icon: 'M20 6 V22 M20 22 L28 30' },
  { title: 'Mechanic Shop Transfers', desc: 'Direct pickup from your mechanic and delivery to your home, or vehicle transport between garages.', icon: 'M8 10 H32 V26 H8 Z M8 18 H32 M16 10 V26' },
  { title: 'Long-Distance Transport', desc: 'Stranded far outside the city? We reach outlying roads and remote areas, not just the main highway.', icon: 'M4 30 L14 12 L20 22 L24 16 L36 30 Z' },
  { title: 'Off-Road & Rough Terrain', desc: 'Winch-equipped heavy pickups for sand, gravel, and rough ground where a standard tow truck can\'t go.', icon: 'M6 24 Q14 10 20 24 Q26 38 34 24' },
  { title: '24/7 Emergency Dispatch', desc: 'Day or night, our line stays open. Call or WhatsApp us and we\'ll route the nearest available unit.', icon: 'circle cx=20 cy=20 r=14 / M20 12 V20 L26 24' },
]

function ServiceIcon({ d }) {
  if (d.startsWith('circle')) {
    return (
      <svg className="icon" viewBox="0 0 40 40" fill="none">
        <circle cx="20" cy="20" r="14" stroke="currentColor" strokeWidth="1.8" />
        <path d="M20 12 V20 L26 24" stroke="currentColor" strokeWidth="1.8" strokeLinecap="round" />
      </svg>
    )
  }
  return (
    <svg className="icon" viewBox="0 0 40 40" fill="none">
      <path d={d} stroke="currentColor" strokeWidth="1.8" fill="none" strokeLinejoin="round" strokeLinecap="round" />
    </svg>
  )
}

function Services() {
  return (
    <section id="services">
      <div className="wrap">
        <div className="section-head">
          <Eyebrow>What We Do</Eyebrow>
          <h2>Recovery for every kind of stuck.</h2>
          <p>From a fender-bender on the highway to a car that won't start outside town — we send the right truck for the job.</p>
        </div>
        <div className="services-grid">
          {SERVICES.map((s) => (
            <div className="service-card" key={s.title}>
              <ServiceIcon d={s.icon} />
              <h3>{s.title}</h3>
              <p>{s.desc}</p>
            </div>
          ))}
        </div>
      </div>
    </section>
  )
}

const FLEET = [
  {
    tag: 'UNIT-01',
    name: 'Flatbed Tow Truck',
    desc: 'Full-bed loading keeps damaged or low-clearance vehicles off their own wheels — the safest option after an accident.',
    specs: [['3.5T', 'Capacity'], ['Hydraulic', 'Bed Tilt'], ['City + Highway', 'Coverage']],
    svg: (
      <svg viewBox="0 0 260 130" width="100%">
        <rect x="0" y="95" width="260" height="8" fill="#3A3E49" />
        <rect x="20" y="55" width="150" height="14" fill="#272B36" stroke="#F2A93B" strokeWidth="1.4" />
        <path d="M170 55 L200 55 L216 78 L216 95 L170 95 Z" fill="#272B36" stroke="#F2A93B" strokeWidth="1.4" />
        <rect x="178" y="62" width="22" height="14" rx="2" fill="#15171C" stroke="#F2A93B" strokeWidth="1.1" />
        <rect x="20" y="45" width="150" height="10" fill="#1E212A" stroke="#F2A93B" strokeWidth="1.2" />
        <circle cx="55" cy="98" r="14" fill="#15171C" stroke="#8891A3" strokeWidth="2" />
        <circle cx="190" cy="98" r="14" fill="#15171C" stroke="#8891A3" strokeWidth="2" />
      </svg>
    ),
  },
  {
    tag: 'UNIT-02',
    name: 'Wheel-Lift Tow Truck',
    desc: 'Quick hookup, quick departure. Ideal for street towing, illegally parked vehicles, and short-distance moves.',
    specs: [['2.2T', 'Capacity'], ['Fast', 'Hookup Time'], ['City', 'Coverage']],
    svg: (
      <svg viewBox="0 0 260 130" width="100%">
        <rect x="0" y="95" width="260" height="8" fill="#3A3E49" />
        <path d="M30 60 Q30 50 42 50 L150 50 Q165 50 170 65 L185 80 L185 95 L30 95 Z" fill="#272B36" stroke="#F2A93B" strokeWidth="1.4" />
        <rect x="130" y="58" width="30" height="18" rx="2" fill="#15171C" stroke="#F2A93B" strokeWidth="1.1" />
        <path d="M185 78 L215 62" stroke="#8891A3" strokeWidth="2" />
        <circle cx="215" cy="62" r="3" fill="#F2A93B" />
        <circle cx="60" cy="98" r="14" fill="#15171C" stroke="#8891A3" strokeWidth="2" />
        <circle cx="160" cy="98" r="14" fill="#15171C" stroke="#8891A3" strokeWidth="2" />
      </svg>
    ),
  },
  {
    tag: 'UNIT-03',
    name: 'Heavy-Duty Recovery Pickup',
    desc: 'Winch-equipped for sand, gravel, and rough terrain — built for vehicles stuck well off the main road.',
    specs: [['Winch', 'Equipped'], ['4x4', 'Drivetrain'], ['Off-Road', 'Coverage']],
    svg: (
      <svg viewBox="0 0 260 130" width="100%">
        <rect x="0" y="95" width="260" height="8" fill="#3A3E49" />
        <path d="M20 95 L20 62 L60 62 L72 45 L110 45 L110 62 L165 62 L165 95 Z" fill="#272B36" stroke="#F2A93B" strokeWidth="1.4" />
        <rect x="78" y="50" width="26" height="14" rx="2" fill="#15171C" stroke="#F2A93B" strokeWidth="1.1" />
        <rect x="112" y="66" width="46" height="20" fill="#1E212A" stroke="#8891A3" strokeWidth="1.2" />
        <circle cx="48" cy="98" r="15" fill="#15171C" stroke="#8891A3" strokeWidth="2" />
        <circle cx="140" cy="98" r="15" fill="#15171C" stroke="#8891A3" strokeWidth="2" />
      </svg>
    ),
  },
]

function Fleet() {
  return (
    <section id="fleet">
      <div className="wrap">
        <div className="section-head">
          <Eyebrow>Our Fleet</Eyebrow>
          <h2>Pickup trucks & tow trucks on call.</h2>
          <p>Every unit is matched to the job — request the right one when you contact us, or leave it to dispatch.</p>
        </div>
        <div className="fleet-grid">
          {FLEET.map((f) => (
            <div className="fleet-card" key={f.tag}>
              <div className="fleet-art">
                <span className="fleet-tag">{f.tag}</span>
                {f.svg}
              </div>
              <div className="fleet-body">
                <h3>{f.name}</h3>
                <p>{f.desc}</p>
                <div className="fleet-specs">
                  {f.specs.map(([val, label]) => (
                    <div key={label}><strong>{val}</strong>{label}</div>
                  ))}
                </div>
                <a className="fleet-cta" href={PHONE_TEL}>Request this unit →</a>
              </div>
            </div>
          ))}
        </div>
      </div>
    </section>
  )
}

const STEPS = [
  ['01', 'Call or WhatsApp', 'Reach our dispatch line directly — no app, no account, just a phone call.'],
  ['02', 'Share your location', 'Tell us where you are and what happened, so we send the right truck.'],
  ['03', 'We dispatch a unit', 'The nearest available pickup or tow truck is sent straight to you.'],
  ['04', 'Vehicle recovered', 'Your car is towed to your mechanic, home, or destination of choice.'],
]

function HowItWorks() {
  return (
    <section id="how">
      <div className="wrap">
        <div className="section-head">
          <Eyebrow>Process</Eyebrow>
          <h2>From call to curbside in four steps.</h2>
        </div>
        <div className="steps">
          {STEPS.map(([num, title, desc]) => (
            <div className="step" key={num}>
              <span className="num">{num}</span>
              <h3>{title}</h3>
              <p>{desc}</p>
            </div>
          ))}
        </div>
      </div>
    </section>
  )
}

const VALUES = [
  ['Always On', 'Dispatch line open 24 hours a day, every day of the week.'],
  ['Right Truck', 'Flatbed, wheel-lift, or heavy pickup — matched to your situation.'],
  ['Wide Reach', 'City streets, highways, and roads well outside town.'],
  ['Direct Contact', 'Speak to a real person — no automated menus.'],
]

function About() {
  return (
    <section id="about" className="about">
      <div className="wrap about-grid">
        <div>
          <Eyebrow>About Recovery Point</Eyebrow>
          <h2 className="about-h2">Built on trust, moving toward a network.</h2>
          <p>Recovery Point started the way most reliable services do — through people who trusted us to show up. Word of mouth, mechanic referrals, and direct contact with friends and drivers on the road built our reputation before we ever needed a website.</p>
          <p>Now we're opening that same trusted service to anyone who needs it. Whether you found us through a friend, a mechanic, or this page, the response is the same: a real truck, sent to your real location, as fast as possible.</p>
          <p>We're growing our network of pickup trucks and tow trucks to cover more roads, more breakdowns, and more accidents — so no one is left waiting on the roadside.</p>
        </div>
        <div className="about-values">
          {VALUES.map(([title, desc]) => (
            <div className="value" key={title}>
              <strong>{title}</strong>
              <span>{desc}</span>
            </div>
          ))}
        </div>
      </div>
    </section>
  )
}

function ContactForm() {
  const [name, setName] = useState('')
  const [location, setLocation] = useState('')
  const [issue, setIssue] = useState('')

  const handleSubmit = (e) => {
    e.preventDefault()
    const msg = `Hi Recovery Point, I need a tow.\nName: ${name}\nLocation: ${location}\nIssue: ${issue || 'N/A'}`
    const url = 'https://wa.me/96668667886?text=' + encodeURIComponent(msg)
    window.open(url, '_blank')
  }

  return (
    <form onSubmit={handleSubmit}>
      <div className="form-group">
        <label htmlFor="name">Your Name</label>
        <input id="name" type="text" placeholder="Full name" value={name} onChange={(e) => setName(e.target.value)} required />
      </div>
      <div className="form-group">
        <label htmlFor="location">Your Location</label>
        <input id="location" type="text" placeholder="Nearest landmark, street, or coordinates" value={location} onChange={(e) => setLocation(e.target.value)} required />
      </div>
      <div className="form-group">
        <label htmlFor="issue">What Happened</label>
        <textarea id="issue" placeholder="e.g. Car won't start, broke down near the highway exit" value={issue} onChange={(e) => setIssue(e.target.value)} />
      </div>
      <button type="submit" className="btn btn-wa form-submit">Send via WhatsApp →</button>
    </form>
  )
}

function Contact() {
  return (
    <section id="contact">
      <div className="wrap">
        <div className="section-head">
          <Eyebrow>Get Recovered</Eyebrow>
          <h2>Stuck right now? Reach us directly.</h2>
          <p>The fastest way to reach us is by phone or WhatsApp. Prefer to send details first? Use the form below.</p>
        </div>
        <div className="contact-grid">
          <div className="contact-direct">
            <Eyebrow>Direct Line</Eyebrow>
            <span className="phone-big">{PHONE}</span>
            <a className="btn btn-call full-btn" href={PHONE_TEL}>Call Now</a>
            <a className="btn btn-wa full-btn" href={WA_LINK} target="_blank" rel="noopener">WhatsApp Us</a>
            <a className="btn btn-ghost full-btn" href="mailto:info@recoverypoint.example">Email Us</a>
          </div>
          <ContactForm />
        </div>
      </div>
    </section>
  )
}

function Footer() {
  return (
    <footer>
      <div className="wrap footer-grid">
        <div className="brand">
          <Logo size={30} />
          <div className="brand-word" style={{ fontSize: '0.95rem' }}>RECOVERY <span>POINT</span></div>
        </div>
        <div className="footer-links">
          <a href="#services">Services</a>
          <a href="#fleet">Fleet</a>
          <a href="#about">About</a>
          <a href={PHONE_TEL}>{PHONE}</a>
        </div>
        <div className="copy">© 2026 Recovery Point. All rights reserved.</div>
      </div>
    </footer>
  )
}

export default function App() {
  const [menuOpen, setMenuOpen] = useState(false)
  return (
    <>
      <Header menuOpen={menuOpen} setMenuOpen={setMenuOpen} />
      <Hero />
      <Ticker />
      <Services />
      <div className="wrap"><div className="road-line" /></div>
      <Fleet />
      <HowItWorks />
      <About />
      <Contact />
      <Footer />
    </>
  )
}
