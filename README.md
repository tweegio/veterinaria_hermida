🐾 Sistema de Gestión Veterinaria
Sistema web completo para la administración de turnos e historias clínicas en veterinarias. Desarrollado con tecnologías web estándar (HTML, CSS, JavaScript) y Firebase Firestore.
🎯 Características

📅 Gestión de Turnos: Administra los turnos del día con estados en tiempo real (espera, atendiendo, completado)
🐕 Registro de Pacientes: Base de datos completa de mascotas y sus dueños
📋 Historia Clínica: Seguimiento detallado de consultas, diagnósticos y tratamientos
🔍 Búsqueda Inteligente: Encuentra pacientes rápidamente por nombre de mascota o dueño
📱 Diseño Responsivo: Funciona perfectamente en computadoras, tablets y móviles
☁️ Almacenamiento en la Nube: Datos seguros y accesibles desde cualquier lugar con Firebase

🚀 Demo en Vivo
👉 Ver Demo (actualizar con tu URL de Vercel)
📸 Capturas de Pantalla
Mostrar imagen
Mostrar imagen
Mostrar imagen
🛠️ Tecnologías Utilizadas

Frontend: HTML5, CSS3, JavaScript (Vanilla)
Backend: Firebase Firestore
Hosting: Vercel
Control de Versiones: Git & GitHub

⚙️ Instalación y Configuración
Prerrequisitos

Una cuenta de Firebase
Una cuenta de Vercel (opcional, para deployment)
Git instalado en tu computadora

Paso 1: Clonar el Repositorio
bashgit clone https://github.com/tu-usuario/sistema-veterinaria.git
cd sistema-veterinaria
Paso 2: Configurar Firebase

Ve a Firebase Console
Crea un nuevo proyecto
Habilita Firestore Database:

Ve a Firestore Database en el menú lateral
Haz clic en "Crear base de datos"
Selecciona "Comenzar en modo de prueba" (para desarrollo)
Elige una ubicación cercana a tu región


Obtén las credenciales de tu app web:

Ve a Configuración del proyecto (ícono de engranaje)
En "Tus aplicaciones", selecciona "Web" (ícono </>)
Registra tu app con un nombre
Copia el objeto de configuración firebaseConfig



Paso 3: Configurar la Aplicación

Abre el archivo index.html en un navegador
Ve a la pestaña "⚙️ Configuración"
Pega tu configuración de Firebase en formato JSON:

json{
  "apiKey": "tu-api-key",
  "authDomain": "tu-proyecto.firebaseapp.com",
  "projectId": "tu-proyecto-id",
  "storageBucket": "tu-proyecto.appspot.com",
  "messagingSenderId": "123456789",
  "appId": "tu-app-id"
}

Haz clic en "💾 Guardar Configuración"
¡Listo! Ya puedes usar la aplicación

🌐 Desplegar en Vercel
Opción 1: Deploy desde GitHub (Recomendado)

Sube tu código a GitHub
Ve a Vercel
Haz clic en "New Project"
Importa tu repositorio de GitHub
Haz clic en "Deploy"
¡Tu app estará en línea en segundos!

Opción 2: Deploy desde CLI
bash# Instalar Vercel CLI
npm i -g vercel

# Hacer deploy
vercel

# Para deploy en producción
vercel --prod
📖 Uso de la Aplicación
Gestión de Turnos

Ve a la pestaña "📅 Turnos del Día"
Haz clic en "+ Nuevo Turno"
Selecciona el paciente, fecha, hora y motivo
Los turnos aparecerán ordenados por hora de llegada
Cambia el estado según el progreso: Espera → Atendiendo → Completado

Registro de Pacientes

Ve a la pestaña "🐕 Pacientes"
Haz clic en "+ Nuevo Paciente"
Completa los datos de la mascota y el dueño
Usa la barra de búsqueda para encontrar pacientes rápidamente

Historia Clínica

En la lista de pacientes, haz clic en "Ver Historia Clínica"
Revisa todas las consultas previas
Haz clic en "+ Agregar Consulta" para registrar una nueva visita
Incluye: fecha, peso, temperatura, diagnóstico, tratamiento y observaciones

🔒 Seguridad en Firebase
Para producción, configura reglas de seguridad en Firestore:
javascriptrules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Regla básica - ajusta según tus necesidades
    match /{document=**} {
      allow read, write: if request.auth != null;
    }
    
    // O para acceso público (solo para pruebas)
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
📂 Estructura del Proyecto
sistema-veterinaria/
│
├── index.html          # Aplicación principal
├── README.md           # Este archivo
├── .gitignore          # Archivos a ignorar en Git
└── screenshots/        # Capturas de pantalla (opcional)
    ├── turnos.png
    ├── pacientes.png
    └── historial.png
🗃️ Estructura de Datos en Firestore
Colección: turnos
javascript{
  pacienteId: "abc123",
  fecha: "2026-01-16",
  hora: "10:30",
  motivo: "Control general",
  estado: "espera", // espera | atendiendo | completado
  timestamp: "2026-01-16T10:00:00.000Z"
}
Colección: pacientes
javascript{
  nombreMascota: "Rocky",
  especie: "Perro",
  raza: "Labrador",
  edad: "3 años",
  sexo: "Macho",
  nombreDueno: "Juan Pérez",
  telefono: "1234567890",
  email: "juan@email.com",
  direccion: "Calle Falsa 123",
  fechaRegistro: "2026-01-16T10:00:00.000Z"
}
Colección: consultas
javascript{
  pacienteId: "abc123",
  fecha: "2026-01-16",
  peso: 25.5,
  temperatura: 38.5,
  motivo: "Control de rutina",
  diagnostico: "Estado general saludable",
  tratamiento: "Vacuna antirrábica",
  observaciones: "Próximo control en 6 meses"
}
🤝 Contribuir
¡Las contribuciones son bienvenidas! Si quieres mejorar este proyecto:

Haz un Fork del proyecto
Crea una rama para tu feature (git checkout -b feature/AmazingFeature)
Commit tus cambios (git commit -m 'Add some AmazingFeature')
Push a la rama (git push origin feature/AmazingFeature)
Abre un Pull Request

📝 Roadmap

 Sistema de autenticación de usuarios
 Recordatorios automáticos por SMS/Email
 Exportación de reportes en PDF
 Gráficos estadísticos
 Gestión de inventario de medicamentos
 Sistema de facturación
 Modo offline con sincronización

🐛 Reportar Problemas
Si encuentras algún bug o tienes alguna sugerencia, por favor abre un issue.
📄 Licencia
Este proyecto está bajo la Licencia MIT - ver el archivo LICENSE para más detalles.
👤 Autor
Tu Nombre

GitHub: [@tweegio]: https://github.com/tweegio
Email: tweegiodeveloper@gmail.com

🙏 Agradecimientos

Inspirado en la necesidad de digitalizar veterinarias que aún usan fichas en papel
Firebase por proporcionar una plataforma backend gratuita y poderosa
Vercel por el hosting gratuito y deployment sencillo


⭐ Si este proyecto te fue útil, considera darle una estrella en GitHub
🐾 Hecho con ❤️ para veterinarias

