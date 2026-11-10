# Crisis asmática pediátrica

Servicio de Pediatría y Neonatología · Hospital de la Axarquía

Aplicación web (HTML + JavaScript, sin dependencias externas) basada en el protocolo
*Manejo de la crisis asmática en la infancia y la adolescencia* (v1.1, 31 de octubre de 2026).
Funciona en iPhone, Android y ordenador. No guarda ni envía datos del paciente.

**Dirección de la app:** https://jmramons.github.io/calculadora-asma/

## Archivos

| Archivo | Función |
|---|---|
| `index.html` | La aplicación completa (plan, escalas, dosis, información) |
| `manifest.webmanifest`, `sw.js` | Permiten instalarla como app y usarla sin conexión |
| `icon-180.png`, `icon-192.png`, `icon-512.png` | Iconos de la app |

## Cómo usarla

- **Ordenador**: doble clic en `index.html` (funciona sin servidor).
- **Móvil**: publicar la carpeta en una dirección https (GitHub Pages, Netlify Drop o intranet) y,
  desde Safari, Compartir → «Añadir a pantalla de inicio». Una vez instalada funciona sin conexión.

## Actualizar

Tras modificar `index.html`, cambiar `VERSION` en `sw.js` (p. ej. `asma-v1.1`) para que los móviles
descarguen la nueva versión.

## Lógica principal

- Peso estimado por edad (APLS) si no se conoce.
- Gravedad = la mayor de: PS + SatO₂ (SEUP: grave PS 7–9 o SatO₂ < 91 %; moderada PS 4–6 o SatO₂ 91–94 %),
  PRAM (0–3 / 4–7 / 8–12; 11–12 riesgo vital), PEF (> 70 / 50–70 / < 50 %) y signos de riesgo vital.
  Puede fijarse a mano; se avisa si es menor que la calculada.
- Plan de grave a leve (apartado 7 del protocolo), con escalada si no hay respuesta a la hora,
  anafilaxia, criterios de ingreso/UCIP/alta y tratamiento al alta.
- Dosis y topes de la Tabla 9 (prednisolona por edad 20/30/40 mg; dexametasona 12 mg; MgSO₄ 2 g y solo ≥ 2 años;
  salbutamol nebulizado 5 mg; continuo 0,3–0,5 mg/kg/h, máx. 15 mg/h).
- Verificada: la tabla por peso generada por la app coincide con las Tablas 10 y 8c del protocolo.

> Herramienta de apoyo: no sustituye al juicio clínico. Revise cada prescripción antes de administrarla.
