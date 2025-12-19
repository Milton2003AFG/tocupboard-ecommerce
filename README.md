# 🛒 ToCupboard E-commerce

## 📋 Descripción del Proyecto

**ToCupboard** es un sitio web de comercio electrónico desarrollado como proyecto académico para demostrar la implementación del modelo **DevSecOps**, integrando llamadas a APIs externas y simulación de pasarela de pagos.

### ✨ Características Principales

- 🌐 **Sitio Web Responsive**: Diseño adaptable a dispositivos móviles y escritorio
- 🔌 **Integración con API**: Consumo de productos desde FakeStore API
- 💳 **Pasarela de Pagos Simulada**: Proceso completo de checkout con validación
- 🛡️ **Seguridad Implementada**: Buenas prácticas de seguridad web
- 📦 **Carrito de Compras**: Sistema completo de gestión de productos

---

## 🚀 Demo en Vivo

👉 **[Ver Sitio Web](https://tuusuario.github.io/tocupboard-ecommerce/)**

---

## 📁 Estructura del Proyecto

```
tocupboard-ecommerce/
│
├── index.html          # Página principal
├── productos.html      # Catálogo de productos (API)
├── carrito.html        # Carrito de compras
├── checkout.html       # Proceso de pago
├── contacto.html       # Formulario de contacto
└── README.md          # Este archivo
```

---

## 🔌 Integración con API

### FakeStore API

El sitio consume datos en tiempo real desde **[FakeStore API](https://fakestoreapi.com/)**:

```javascript
// Llamada a la API
const response = await fetch('https://fakestoreapi.com/products?limit=8');
const products = await response.json();
```

### Endpoints Utilizados

| Endpoint | Método | Descripción |
|----------|--------|-------------|
| `/products` | GET | Obtiene lista de productos |
| `/products?limit=8` | GET | Limita a 8 productos |

---

## 💳 Pasarela de Pagos Simulada

### Características de Seguridad

- ✅ **Validación de Formularios**: Todos los campos son requeridos
- ✅ **Formato de Tarjeta**: Validación de número de tarjeta (XXXX XXXX XXXX XXXX)
- ✅ **Fecha de Expiración**: Formato MM/AA
- ✅ **CVV**: 3 dígitos de seguridad
- ✅ **Encriptación Simulada**: Proceso de pago con indicador de seguridad
- ✅ **Confirmación de Orden**: Generación de número único de pedido

### Flujo de Pago

1. **Selección de Productos** → Agregar al carrito
2. **Revisión de Carrito** → Modificar cantidades
3. **Checkout** → Completar información personal y de envío
4. **Pago** → Seleccionar método y confirmar
5. **Confirmación** → Número de orden generado

---

## 🛡️ Implementación de DevSecOps

### Prácticas de Seguridad Aplicadas

#### 1. **Seguridad en el Desarrollo (Dev)**
- ✅ Validación de datos en frontend
- ✅ Sanitización de inputs
- ✅ No se exponen datos sensibles en el código
- ✅ localStorage para manejo seguro del carrito

#### 2. **Seguridad en Operaciones (Ops)**
- ✅ Hosting en GitHub Pages (HTTPS por defecto)
- ✅ Control de versiones con Git
- ✅ Código abierto para auditoría
- ✅ Documentación completa

#### 3. **Seguridad en el Código (Sec)**
- ✅ No se almacenan datos de tarjetas (solo simulación)
- ✅ Validaciones en tiempo real
- ✅ Manejo de errores apropiado
- ✅ Buenas prácticas de JavaScript

### Modelo DevSecOps Aplicado

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│    DEV      │────>│     SEC     │────>│     OPS     │
│ Desarrollo  │     │  Seguridad  │     │  Despliegue │
└─────────────┘     └─────────────┘     └─────────────┘
      │                    │                    │
      └────────────────────┴────────────────────┘
                  Retroalimentación
```

---

## 🔐 Medidas de Seguridad Implementadas

### Frontend Security

| Medida | Implementación |
|--------|----------------|
| **Validación de Formularios** | HTML5 `required`, validación de formato |
| **Sanitización** | Prevención de XSS en inputs |
| **HTTPS** | GitHub Pages con SSL automático |
| **No datos sensibles** | Sin almacenamiento de info de pago |

### API Security

- ✅ Uso de HTTPS para llamadas a API
- ✅ Manejo de errores de red
- ✅ Timeout para solicitudes
- ✅ Validación de respuestas JSON

---

## 🧪 Pruebas de Seguridad

### Checklist de Pruebas Realizadas

- [x] Validación de formularios
- [x] Manejo de errores de API
- [x] Prevención de inyección de código
- [x] Validación de formato de tarjeta
- [x] Verificación de HTTPS
- [x] Prueba de navegación entre páginas
- [x] Funcionalidad de carrito completa
- [x] Proceso de checkout sin errores

---

## 📦 Instalación y Uso

### Opción 1: GitHub Pages (Recomendado)

1. Fork este repositorio
2. Ve a Settings → Pages
3. Selecciona la rama `main` como fuente
4. Tu sitio estará en: `https://tuusuario.github.io/tocupboard-ecommerce/`

### Opción 2: Local

```bash
# Clonar el repositorio
git clone https://github.com/tuusuario/tocupboard-ecommerce.git

# Abrir index.html en tu navegador
cd tocupboard-ecommerce
open index.html
```

---

## 🛠️ Tecnologías Utilizadas

| Tecnología | Propósito |
|------------|-----------|
| **HTML5** | Estructura del sitio |
| **CSS3** | Diseño y estilos responsive |
| **JavaScript** | Lógica de negocio y API |
| **FakeStore API** | Datos de productos |
| **localStorage** | Persistencia del carrito |
| **GitHub Pages** | Hosting gratuito con HTTPS |

---

## 📊 Funcionalidades

### ✅ Páginas Implementadas

- **Inicio**: Landing page con características
- **Productos**: Catálogo dinámico desde API
- **Carrito**: Gestión completa de productos
- **Checkout**: Proceso de pago simulado
- **Contacto**: Formulario de comunicación

### ✅ Características del Carrito

- Agregar productos
- Modificar cantidades (+/-)
- Eliminar productos
- Cálculo automático de totales
- Persistencia con localStorage

### ✅ Características del Checkout

- Información personal
- Dirección de envío
- Selección de método de pago
- Validación de tarjeta
- Confirmación de orden

---

## 🔄 CI/CD Pipeline (Propuesto)

```yaml
# Ejemplo de GitHub Actions para despliegue automático
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./
```

---

## 📈 Monitoreo y Mejoras Futuras

### Próximas Implementaciones

- [ ] Integración con pasarela real (Stripe/PayPal)
- [ ] Base de datos para productos propios
- [ ] Sistema de autenticación de usuarios
- [ ] Panel de administración
- [ ] Pruebas automatizadas (Jest)
- [ ] Análisis de vulnerabilidades con Snyk
- [ ] Logs de auditoría
- [ ] Notificaciones por email

---

## 👨‍💻 Autor

**Milton Flores**  
Proyecto Académico - Modelo DevSecOps  
Diciembre 2025

---

## 📄 Licencia

Este proyecto es de código abierto y está disponible para fines educativos.

---

## 🤝 Contribuciones

Este es un proyecto académico, pero si deseas sugerir mejoras:

1. Fork el proyecto
2. Crea una rama (`git checkout -b feature/mejora`)
3. Commit tus cambios (`git commit -m 'Agrega nueva característica'`)
4. Push a la rama (`git push origin feature/mejora`)
5. Abre un Pull Request

---

## 📞 Contacto

Para preguntas o sugerencias sobre el proyecto:

- 📧 Email: milton.flores@ejemplo.com
- 🌐 GitHub: [@tuusuario](https://github.com/tuusuario)

---

## 🎓 Contexto Académico

Este proyecto fue desarrollado como parte de la actividad de aprendizaje sobre **DevSecOps** para demostrar:

1. Integración de APIs externas
2. Implementación de pasarela de pagos
3. Buenas prácticas de seguridad web
4. Desarrollo de aplicaciones seguras
5. Documentación técnica

---

## 🔍 Referencias

- [FakeStore API Documentation](https://fakestoreapi.com/docs)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [GitHub Pages](https://pages.github.com/)
- [DevSecOps Best Practices](https://www.devsecops.org/)

---

⭐ **Si este proyecto te fue útil, no olvides darle una estrella en GitHub**