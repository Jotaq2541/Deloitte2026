
:root {
  --bg: #0b0c10;
  --panel: #111317;
  --card: #141821;
  --primary: #86c232;
  --text: #e6e6e6;
  --muted: #9aa0a6;
  --danger: #ff6b6b;
  --ok: #2ecc71;
  --accent: #3a82f6;
}
* { box-sizing: border-box }
html, body { height: 100% }
body {
  margin: 0;
  color: var(--text);
  background: radial-gradient(1200px 600px at 20% 0%, #0e1117 0%, var(--bg) 60%);
  font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, "Helvetica Neue", sans-serif;
  display: grid; grid-template-rows: auto 1fr auto; gap: 12px;
}
header, footer { padding: 12px 16px; background: transparent }
header { display: flex; align-items: center; justify-content: space-between }
.brand { display: flex; align-items: center; gap: 12px }
.brand h1 { margin: 0; font-size: 16px; font-weight: 600; letter-spacing: .2px }
.row { display: flex; gap: 8px; align-items: center; flex-wrap: wrap }
label { font-size: 12px; color: var(--muted) }
select, button, input[type="text"] {
  background: #0f1216; color: var(--text);
  border: 1px solid rgba(255,255,255,0.14);
  border-radius: 8px; padding: 8px 10px; font-size: 14px;
}
button { cursor: pointer }
.btn-primary {
  background: linear-gradient(180deg, #1f2937, #0f1216);
  border: 1px solid rgba(134,194,50,0.4);
  box-shadow: inset 0 1px 0 rgba(255,255,255,0.06), 0 0 0 2px rgba(134,194,50,0.12);
}
.pill { padding: 4px 8px; border-radius: 999px; font-size: 11px; border: 1px solid rgba(255,255,255,0.12) }
.ok { color: var(--ok); border-color: rgba(46,204,113,0.35) }
.err { color: var(--danger); border-color: rgba(255,107,107,0.35) }

.wrap {
  display: grid; grid-template-columns: 360px 1fr; gap: 16px; padding: 0 16px 16px; min-height: 0;
}
@media (max-width: 980px) { .wrap { grid-template-columns: 1fr } }
.left, .right {
  background: linear-gradient(180deg, rgba(255,255,255,0.02), transparent 180px);
  border: 1px solid rgba(255,255,255,0.06); border-radius: 14px; min-height: 0;
}
.left { padding: 14px; display: grid; grid-template-rows: auto auto 1fr; gap: 14px }
.right { display: grid; grid-template-rows: auto 1fr auto }
.card {
  background: var(--card);
  border: 1px solid rgba(255,255,255,0.06);
  border-radius: 12px; padding: 12px;
}
.switches { display: flex; gap: 8px; flex-wrap: wrap }
.switches label { display: flex; align-items: center; gap: 6px; background: #0f1216; padding: 6px 8px; border-radius: 8px; border: 1px solid rgba(255,255,255,0.06) }

.chat-header { padding: 12px 14px; border-bottom: 1px solid rgba(255,255,255,0.06); display: flex; align-items: center; justify-content: space-between }
.chat { overflow: auto; padding: 14px; display: grid; gap: 10px; align-content: start; background: rgba(0,0,0,0.22) }
.msg { display: grid; gap: 6px; max-width: 90% }
.me { justify-self: end }
.bubble {
  padding: 10px 12px; border-radius: 12px; line-height: 1.35; white-space: pre-wrap;
  border: 1px solid rgba(255,255,255,0.06); background: #12151b;
}
.me .bubble { background: #10141a; border-color: rgba(58,130,246,0.35) }
.ai .bubble { background: #121a12; border-color: rgba(134,194,50,0.35) }
.meta { font-size: 11px; color: var(--muted) }
.citas { font-size: 12px; margin-top: 6px; color: #b8c3b8 }
.composer { display: grid; grid-template-columns: 1fr auto auto; gap: 8px; padding: 12px; border-top: 1px solid rgba(255,255,255,0.06) }
.disclaimer { font-size: 12px; color: var(--muted); padding: 8px 12px }

/* Avatar holográfico */
.avatar {
  position: relative; aspect-ratio: 4/5; border-radius: 12px; overflow: hidden; background: #07090d;
  border: 1px solid rgba(134,194,50,0.25);
  box-shadow: 0 0 0 1px rgba(134,194,50,0.08), 0 18px 60px rgba(0,0,0,0.35);
}
#avatarVideo {
  width: 100%; height: 100%; object-fit: cover; display: block; filter: contrast(1.05) saturate(1.02) hue-rotate(2deg);
}
.scanlines {
  position: absolute; inset: 0; pointer-events: none;
  background:
    linear-gradient(rgba(0,255,255,0.06), rgba(0,0,0,0) 2px),
    repeating-linear-gradient(0deg, rgba(0,255,180,0.08), rgba(0,255,180,0.08) 1px, transparent 1px, transparent 3px);
  mix-blend-mode: screen; animation: sweep 4s linear infinite;
}
@keyframes sweep {
  0% { background-position: 0 0, 0 0; }
  100% { background-position: 0 100%, 0 0; }
}
/* “Hablando” (ligero glow) */
.talking {
  box-shadow: 0 0 0 1px rgba(134,194,50,0.18), 0 0 25px rgba(134,194,50,0.35), 0 18px 60px rgba(0,0,0,0.35);
}
.subtitle {
  position: absolute; bottom: 8px; left: 8px; right: 8px; background: rgba(0,0,0,0.45); backdrop-filter: blur(4px);
  padding: 6px 8px; border-radius: 8px; font-size: 12px; color: #e9eefc; text-shadow: 0 1px 2px #000;
  max-height: 38%; overflow: auto;
}
