# Falco Insights - Web Corporativa

## Contexto de la Empresa

**Falco Insights** es una empresa española de servicios de inteligencia especializada en inteligencia reputacional, influencia y contrainfluencia. El equipo fundador proviene del mundo del análisis de inteligencia y la psicología, no de la ingeniería de software.

**Claim:** "Miramos más allá para que tú decidas mejor"

**Misión:** Detectar y neutralizar campañas de manipulación cognitiva con IA, psicología e inteligencia.

### Equipo

| Nombre | Cargo | Email |
|--------|-------|-------|
| Guillermo Barrón Morera | CEO | gbarron@falcoinsights.com |
| Hugo Zunzarren Denis | COO | hzunzarren@falcoinsights.com |
| Adrián Sánchez Camón | CTO | asanchez@falcoinsights.com |
| Rafael Calvo Garcia | CMO | rcalvo@falcoinsights.com |
| Sonia Fernández Palma | RRII | sfernandez@falcoinsights.com |
| General | — | contacto@falcoinsights.com |

### Áreas de Especialización
1. **Análisis de inteligencia**: reputacional, competitiva, tecnológica, militar, seguridad
2. **Influencia y contrainfluencia**: psicología operativa, guerra cognitiva, PSYOPS
3. **Tecnología**: IA generativa, plataforma Influenza

### Modelo de Negocio (dos patas)
1. **Consultoría especializada**: Servicios ad hoc de monitorización de campañas de manipulación, inteligencia estratégica, due diligence, background checks, análisis de competencia, investigación de imagen de marca
2. **Influenza (SaaS)**: Plataforma propietaria de inteligencia que automatiza detección, análisis y mitigación de campañas de manipulación informativa

### Clientes Objetivo
- Instituciones de inteligencia y defensa
- Gobiernos e instituciones públicas
- Empresas y corporaciones
- Medios de comunicación

---

## Influenza - La Plataforma

Influenza es una plataforma de inteligencia avanzada desarrollada por Falco Insights. Es el primer sistema de protección contra la manipulación informativa basado en psicología operativa, análisis de inteligencia y conocimiento experto en guerra cognitiva, PSYOPS y desinformación.

### Flujo de la plataforma
1. **Motor de monitorización** - Ingesta continua de piezas informativas (redes sociales, prensa, foros, Google News)
2. **Motor de análisis multidimensional** - Análisis de influencia, narrativa y veracidad de cada pieza
3. **Extracción de TTPs** - Modus operandi de influencia, metadatos de actores/entidades, clasificación temática, segmentación en hilos narrativos
4. **Base de datos relacional** - Integración de datos analizados, extracción de métricas, análisis holístico a nivel de campaña
5. **Explorador de insights** - Visualización y emisión de medidas de mitigación y contrainfluencia

### Capacidades Clave
- Detección de variables de influencia y persuasión (Cialdini, FCAME, FUD)
- Análisis de manipulación psicológica y sesgos cognitivos
- Fact-checking automatizado con fuentes trazables
- Monitorización predictiva
- Análisis multimedia (transcripción de imagen, vídeo y audio)
- Integración empresarial

### Diferenciación vs. Competencia
| Dificultad | Propuestas actuales del mercado | Propuesta Falco |
|---|---|---|
| Gran volumen | Fact-checking rudimentario bajo demanda | Monitorización y análisis automatizados |
| Tiempos lentos | Monitorización manual | Gran capacidad de procesamiento |
| Enfoque reactivo | Informes superficiales de contenido | Análisis basado en psicología operativa |
| Complejidad de análisis | Visión atomística | Enfoque holístico (veracidad, TTPs, narrativas) |
| Mitigación genérica | Estrategias débiles y genéricas | Propuestas de mitigación y contrainfluencia |

### Stack Técnico de Influenza (referencia)
- **Backend**: Flask (Python), desplegado en Google Cloud Run (europe-west1)
- **Frontend**: HTML/CSS/JavaScript
- **APIs**: Anthropic Claude (análisis de narrativas) + OpenAI GPT-4o (fact-checking)
- **Base de datos**: PostgreSQL
- **Repositorio backend**: Separado de esta web (directorio backend2_c_25022026)
- **URL producción**: https://influenza-backend-489985541949.europe-west1.run.app

---

## Esta Web - Información Técnica

### Dominio y Hosting
- **Dominio**: falcoinsights.com (primary), www.falcoinsights.com (redirect)
- **Registrador del dominio**: WordPress.com (Automattic Inc.) — pendiente transferir a Cloudflare
- **Hosting**: Netlify (static site hosting, deploy automático desde GitHub)
- **DNS**: Configurados en WordPress.com apuntando a Netlify:
  - A record `@` → `75.2.60.5`
  - CNAME `www` → `apex-loadbalancer.netlify.com`
  - A record `influenza` → `34.49.178.28` (subdominio de la plataforma Influenza en GCP, NO TOCAR)
  - Registros MX → Google (correo corporativo, NO TOCAR)
- **GitHub**: https://github.com/asanchezfalco/falco-insights-web.git
- **Netlify URL**: falcoinsights.netlify.app (subdominio de backup)

### Origen
La web se migró de WordPress a HTML estático usando un plugin de exportación. Por eso conserva estructura de carpetas tipo WordPress (`wp-content/`, `wp-includes/`).

### Estructura del Sitio

```
/
├── index.html                          # Homepage
├── about/index.html                    # Sobre nosotros
├── servicios-de-inteligencia/index.html # Servicios de inteligencia
├── influenza-by-falco-insights/index.html # Página de producto Influenza
├── politica-de-privacidad/index.html   # Política de privacidad
├── terminos-y-condiciones/index.html   # Términos y condiciones
├── 2025/05/18/                         # Blog posts (contenido de prueba)
│   ├── crecimiento-desbloqueado/
│   ├── el-arte-de-la-conexion/
│   ├── magia-de-la-colaboracion/
│   ├── mas-alla-del-obstaculo/
│   ├── triunfo-del-trabajo-en-equipo/
│   └── ventaja-adaptativa/
├── author/                             # Páginas de autor (WordPress legacy)
├── category/                           # Categorías (WordPress legacy)
├── wp-content/                         # Assets de plugins WordPress
└── wp-includes/                        # Assets de sistema WordPress
```

### Páginas Principales
1. **Homepage** (`/`): Presentación de Falco Insights, productos y servicios, fundadores, entidades asociadas
2. **Sobre nosotros** (`/about/`): Descripción de la empresa, áreas de especialización, perfiles de fundadores
3. **Servicios** (`/servicios-de-inteligencia/`): Defensa cognitiva, contra-influencia, consultoría estratégica, inteligencia para alta dirección
4. **Influenza** (`/influenza-by-falco-insights/`): Página de producto de la plataforma Influenza
5. **Legal**: Política de privacidad y términos

### Tema y Estilo
- WordPress TwentyTwentyfour theme (exportado a estático)
- Diseño responsive, mobile-first
- Bloques Gutenberg convertidos a HTML estático
- Idioma: Español (es_ES)

### Notas Importantes
- **Formularios de contacto**: Se eliminaron porque no funcionan en sitios estáticos. Si se quieren recuperar, usar Netlify Forms o un servicio externo.
- **Blog posts**: Los 6 posts en `/2025/05/18/` parecen contenido de prueba/placeholder, no contenido real de la empresa.
- **Legacy WordPress**: Las carpetas `wp-content/` y `wp-includes/` contienen assets necesarios para el estilo y funcionalidad del sitio. No eliminar sin verificar dependencias.

---

## Tareas Pendientes

### 1. Cloudflare ✅ COMPLETADO (2026-03-17)
- [x] Crear cuenta en Cloudflare
- [x] Configurar DNS en Cloudflare (A, CNAME, MX, TXT, subdominio influenza)
- [x] Cambiar nameservers en WordPress.com a devin.ns.cloudflare.com y maisie.ns.cloudflare.com
- [x] Configurar SSL/TLS en modo "Full (Strict)"
- [x] CDN y protección DDoS activos (plan Free)
- [x] Bloqueo de bots de IA activado
- [ ] Transferir dominio de WordPress.com a Cloudflare (opcional, cuando caduque el plan)

### 2. Limpieza de Google Search ✅ COMPLETADO (2026-03-17)
- [x] Verificar propiedad de falcoinsights.com en Google Search Console
- [x] Retirada de URLs enviada para 6 páginas legacy (procesando, 1-3 días):
  - /consultoria-estrategica/
  - /formacion-profesionalizante/
  - /desarrollohsoftware/
  - /influencia-y-contrainfluencia/
  - /2025/05/18/el-arte-de-la-conexion/
  - /2025/05/18/mas-alla-del-obstaculo/

### 3. Mejoras Web Potenciales
- [ ] Revisar y actualizar contenido del blog (los posts actuales son placeholder)
- [ ] Evaluar si los formularios de contacto deben restaurarse (Netlify Forms)
- [ ] Limpiar assets WordPress innecesarios si es posible
- [ ] Verificar que todas las imágenes y recursos cargan correctamente en producción
- [ ] Cancelar plan de WordPress.com cuando todo funcione correctamente (después de transferir dominio)

---

## Cómo Trabajar en Esta Web

### Flujo de cambios
1. Editar archivos HTML/CSS localmente
2. Commit y push a GitHub
3. Netlify despliega automáticamente desde el repo

### Para probar localmente
```bash
# Servir la web localmente (desde el directorio del repo)
python -m http.server 8000
# Acceder en http://localhost:8000
```

### Convenciones
- Los archivos HTML son autocontenidos (estilos inline del export de WordPress)
- Para cambios de contenido, editar directamente el HTML de la página correspondiente
- Mantener la estructura de URLs actual para no romper enlaces existentes
