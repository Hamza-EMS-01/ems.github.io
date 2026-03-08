import { useState } from "react";

const DARK = "#2C3E50";
const ACCENT = "#95A5A6";
const LIGHT_BG = "#F4F6F7";
const TEXT_MID = "#555555";

const SkillBar = ({ label, level }) => (
  <div style={{ marginBottom: 10 }}>
    <div style={{ color: "white", fontSize: 13, marginBottom: 3 }}>{label}</div>
    <div style={{ color: ACCENT, fontSize: 16, letterSpacing: 3 }}>
      {Array.from({ length: 5 }, (_, i) => (i < level ? "●" : "○")).join("")}
    </div>
  </div>
);

const LeftSection = ({ title, children }) => (
  <div style={{ marginBottom: 20 }}>
    <div style={{
      color: "white", fontWeight: "bold", fontSize: 12, letterSpacing: 2,
      textTransform: "uppercase", borderBottom: `1px solid ${ACCENT}`,
      paddingBottom: 5, marginBottom: 12
    }}>{title}</div>
    {children}
  </div>
);

const RightSection = ({ title, children }) => (
  <div style={{ marginBottom: 24 }}>
    <div style={{
      color: DARK, fontWeight: "bold", fontSize: 13, letterSpacing: 2,
      textTransform: "uppercase", borderBottom: `2px solid ${DARK}`,
      paddingBottom: 5, marginBottom: 14
    }}>{title}</div>
    {children}
  </div>
);

const ExpEntry = ({ title, company, period, bullets }) => (
  <div style={{ marginBottom: 18 }}>
    <div style={{ fontWeight: "bold", fontSize: 14, color: DARK }}>{title}</div>
    <div style={{ fontSize: 12, marginBottom: 6 }}>
      <span style={{ fontWeight: "bold", color: "#34495E" }}>{company}</span>
      <span style={{ color: ACCENT, fontStyle: "italic", marginLeft: 8 }}>{period}</span>
    </div>
    {bullets.map((b, i) => (
      <div key={i} style={{ fontSize: 12, color: TEXT_MID, paddingLeft: 12, marginBottom: 3 }}>
        – {b}
      </div>
    ))}
  </div>
);

export default function Resume() {
  return (
    <div style={{ fontFamily: "Arial, sans-serif", display: "flex", height: "100vh", overflow: "auto" }}>
      {/* LEFT COLUMN */}
      <div style={{
        width: 260, minWidth: 260, background: DARK, color: "white",
        padding: "30px 20px", boxSizing: "border-box"
      }}>
        {/* Name */}
        <div style={{ textAlign: "center", marginBottom: 30 }}>
          <div style={{ fontSize: 26, fontWeight: "bold" }}>Camille</div>
          <div style={{ fontSize: 26, fontWeight: "bold" }}>DUPONT</div>
          <div style={{ color: ACCENT, fontStyle: "italic", fontSize: 12, marginTop: 6 }}>
            Full-Stack Web Developer
          </div>
        </div>

        <LeftSection title="Contact">
          {[
            ["📧", "candidat@exemple.com"],
            ["💼", "linkedin.com/in/yourprofile"],
            ["💻", "github.com/yourusername"],
            ["📍", "Paris, France"],
          ].map(([icon, text]) => (
            <div key={text} style={{ fontSize: 12, marginBottom: 8, color: "#ddd" }}>
              {icon} {text}
            </div>
          ))}
        </LeftSection>

        <LeftSection title="Compétences">
          <div style={{ color: ACCENT, fontSize: 11, fontWeight: "bold", marginBottom: 8 }}>FRONT-END</div>
          <SkillBar label="ReactJS / VueJS / Nuxt.js" level={5} />
          <SkillBar label="TypeScript / JavaScript" level={5} />
          <SkillBar label="HTML5 / CSS3" level={4} />
          <div style={{ color: ACCENT, fontSize: 11, fontWeight: "bold", margin: "10px 0 8px" }}>BACK-END</div>
          <SkillBar label="Node.js / Express.js" level={5} />
          <SkillBar label="PHP (Symfony/Laravel)" level={4} />
          <SkillBar label="Python / Django" level={4} />
          <SkillBar label="GraphQL / REST APIs" level={5} />
          <div style={{ color: ACCENT, fontSize: 11, fontWeight: "bold", margin: "10px 0 8px" }}>DEVOPS & CLOUD</div>
          <SkillBar label="AWS / Firebase" level={3} />
          <SkillBar label="GitLab CI/CD" level={4} />
          <SkillBar label="Docker" level={3} />
        </LeftSection>

        <LeftSection title="Formation">
          {[
            { degree: "Diplôme Ingénieur", school: "EFREI Paris", year: "2016–2019", note: "Data Science" },
            { degree: "DUT Informatique", school: "IUT d'Orsay", year: "2015–2016" },
            { degree: "Baccalauréat S", school: "Lycée Janson de Sailly", year: "2015", note: "Mention Bien" },
          ].map((e) => (
            <div key={e.school} style={{ marginBottom: 12 }}>
              <div style={{ fontWeight: "bold", fontSize: 12 }}>{e.degree}</div>
              <div style={{ color: ACCENT, fontSize: 11, fontStyle: "italic" }}>{e.school} · {e.year}</div>
              {e.note && <div style={{ fontSize: 11, color: "#ccc" }}>{e.note}</div>}
            </div>
          ))}
        </LeftSection>

        <LeftSection title="Langues">
          <div style={{ marginBottom: 8 }}>
            <div style={{ fontWeight: "bold", fontSize: 12 }}>Anglais – C1</div>
            <div style={{ color: ACCENT, fontSize: 11 }}>Stage 6 mois au Royaume-Uni</div>
          </div>
          <div>
            <div style={{ fontWeight: "bold", fontSize: 12 }}>Espagnol – B1</div>
            <div style={{ color: ACCENT, fontSize: 11 }}>Niveau conversationnel</div>
          </div>
        </LeftSection>

        <LeftSection title="Intérêts">
          {["🏓 Tennis de table", "📚 Lecture", "🎬 Cinéma", "✏️ Dessin"].map(i => (
            <div key={i} style={{ fontSize: 12, marginBottom: 6, color: "#ddd" }}>{i}</div>
          ))}
        </LeftSection>
      </div>

      {/* RIGHT COLUMN */}
      <div style={{ flex: 1, background: LIGHT_BG, padding: "30px 28px", overflowY: "auto" }}>
        <RightSection title="À propos">
          <p style={{ fontSize: 13, color: TEXT_MID, lineHeight: 1.6, margin: 0 }}>
            Développeur full-stack passionné, diplômé ingénieur informatique à l'EFREI Paris. Fort d'expériences chez Instagram, Thales et Sopra Steria, je conçois des architectures back-end robustes et des interfaces front-end modernes. À la recherche d'une nouvelle opportunité innovante.
          </p>
        </RightSection>

        <RightSection title="Expériences">
          <ExpEntry
            title="Développeur Back-End (PHP & Node.js)"
            company="Sopra Steria — Paris"
            period="2021 – 2022"
            bullets={[
              "APIs PHP sécurisées avec Symfony et Laravel",
              "Requêtes SQL avancées et ElasticSearch sur grands datasets",
              "Endpoints Express.js sécurisés avec considérations cybersécurité",
              "Intégration AWS en Node.js pour améliorer la scalabilité",
            ]}
          />
          <ExpEntry
            title="Développeur Back-End (Python)"
            company="Thales — Grenoble"
            period="2020 – 2021"
            bullets={[
              "Conception et implémentation d'endpoints GraphQL",
              "Optimisation de traitement massif de documents sur NoSQL",
              "96% des tâches sprint livrées dans les délais",
            ]}
          />
          <ExpEntry
            title="Développeur Front-End (ReactJS)"
            company="Instagram — Paris"
            period="2019"
            bullets={[
              "Tests unitaires automatisés sur composants clés",
              "Refactoring de composants ReactJS en TypeScript",
              "Mise à jour des dépendances et résolution de compatibilité",
            ]}
          />
        </RightSection>

        <RightSection title="Projets">
          {[
            {
              name: "Plateforme Web Full-Stack",
              stack: "React · Node.js · MongoDB · Docker",
              desc: "Plateforme scalable de gestion et visualisation de données, déployée avec containerisation.",
            },
            {
              name: "Dashboard Data Analytics",
              stack: "Vue.js · Django · PostgreSQL",
              desc: "Dashboard analytique agrégeant de grands datasets avec visualisations et rapports automatisés.",
            },
          ].map((p) => (
            <div key={p.name} style={{ marginBottom: 14 }}>
              <div style={{ fontWeight: "bold", fontSize: 14, color: DARK }}>{p.name}</div>
              <div style={{ color: ACCENT, fontStyle: "italic", fontSize: 12, marginBottom: 4 }}>{p.stack}</div>
              <div style={{ fontSize: 12, color: TEXT_MID }}>{p.desc}</div>
            </div>
          ))}
        </RightSection>
      </div>
    </div>
  );
}
