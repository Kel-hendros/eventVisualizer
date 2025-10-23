---
NotebookLLM: true
Fecha de Subida al LLM: 2025-10-22T16:08:00
---

La funcionalidad de Inscripciones permite crear eventos especiales, donde los usuarios ya no son meros expectadores, sino que participan activamente de los mismos.

Las principales diferencias con un evento "normal" son las siguientes:

- Las inscripciones cuentan con un Formulario Dinámico que el usuario debe completar para poder comprar su Inscripción.
- Un usuario solo puede comprar UN solo ticket de una Inscripción, porque solo puede comprarla para sí mismo, a diferencia de otros eventos donde puede comprar muchos tickets e ir acompañado de otras personas. Esto es porque la Inscripción implica completar el formulario y aceptar los Terminos y Condiciones, casi como una declaración jurada, que solo puede aceptarse para uno mismo.
- Los Asesores de Venta de los Organizaciones o de Fanki NO pueden comprar una inscripción por la misma razón, ellos no pueden aceptar los terminos y condiciones en nombre de su cliente.

# Creación de una Inscripción

Se puede crear un evento de Inscripción mediante el siguiente Swagger

http://catalog-service.fankipass.svc.cluster.local/api/catalog-service/swagger-ui/index.html#/inscriptions-controller/create_1

Ahi se pede generar un nuevo evento con la información necesaria, incluyendo el Formulario de Inscripción, usando los campos detallados a continuación.

## Ejemplo de Evento de Inscripción

```JSON
{
  "code": "INS_MARATHON_1",
  "name": "MARATHON TEST",
  "detail": "DETALLES DEL EVENTO",
  "enabled": true,
  "country": "MEX",
  "venue": "En la calle",
  "layout": "LAYOUT_INS_MARATHON_1",
  "type": "INSCRIPTION",
  "date": "2024-12-25 15:30:00",
  "createdAt": "2024-11-21 17:29:04",
  "images": {
    "banner": {
      "small": "https://public-content.bitsports.co/fanki/assets/col/banners/ATL_Nacional/BANNER_APP_DESTACADO_ABN_NAC_CUA_2024II_221124_small.webp",
      "medium": "https://public-content.bitsports.co/fanki/assets/col/banners/ATL_Nacional/BANNER_APP_DESTACADO_ABN_NAC_CUA_2024II_221124_medium.webp",
      "large": "https://public-content.bitsports.co/fanki/assets/col/banners/ATL_Nacional/BANNER_APP_DESTACADO_ABN_NAC_CUA_2024II_221124_medium.webp"
    },
    "background": {
      "small": "https://public-content.bitsports.co/fanki/assets/col/tickets/Cucuta/Ticket_TOR_VS_CIM_201124_medium.webp",
      "medium": "https://public-content.bitsports.co/fanki/assets/col/tickets/Cucuta/Ticket_TOR_VS_CIM_201124_medium.webp",
      "large": "https://public-content.bitsports.co/fanki/assets/col/tickets/Cucuta/Ticket_TOR_VS_CIM_201124_large.webp"
    },
    "header": {
      "small": "string",
      "medium": "string",
      "large": "string"
    }
  },
  "featured": true,
  "accessPolicies": "POLITICAS DE ACCESO",
  "coordinator": "Maraton Company",
  "expired": false,
  "expiredQr": false,
  "qrType": "STATIC_DEFAULT",
  "sponsors": [
    {
      "code": "string",
      "name": "string",
      "image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      }
    }
  ],
  "maxSalesQuantity": 10000,
  "termsAndConditionsUrl": "https://public-content.bitsports.co/fanki/assets/mex/Terms_and_conditions_by_ODe/TyC-KLA-QLA.pdf",
  "cashPaymentDueDays": 0,
  "ticketFrame": {
    "small": "https://public-content.bitsports.co/fanki/assets/mex/TicketFrames/TICKET_FRAME_QL_280924.webp",
    "medium": "https://public-content.bitsports.co/fanki/assets/mex/TicketFrames/TICKET_FRAME_QL_280924.webp",
    "large": "https://public-content.bitsports.co/fanki/assets/mex/TicketFrames/TICKET_FRAME_QL_280924.webp"
  },
  "sponsorBanner": {
    "small": "https://public-content.bitsports.co/fanki/assets/mex/SponsorBanners/BANNER_SPONSOR_QL_280924.webp",
    "medium": "https://public-content.bitsports.co/fanki/assets/mex/SponsorBanners/BANNER_SPONSOR_QL_280924.webp",
    "large": "https://public-content.bitsports.co/fanki/assets/mex/SponsorBanners/BANNER_SPONSOR_QL_280924.webp"
  },
  "inscriptionForm": {
    "fields": [
      {
        "required": true,
        "label": "Nombre Completo",
        "placeholder": "Nombre(s) y Apellido(s)",
        "name": "full_name",
        "type": "TEXT",
        "minLength": 3,
        "maxLength": 100
      },
      {
        "required": true,
        "label": "Fecha de Nacimiento",
        "placeholder": "YYYY-MM-DD",
        "name": "birthdate",
        "type": "DATE"
      },
      {
        "required": true,
        "label": "Sexo",
        "placeholder": "Selecciona tu sexo",
        "name": "gender",
        "type": "SELECT",
        "options": [
          {
            "label": "Masculino",
            "value": "M"
          },
          {
            "label": "Femenino",
            "value": "F"
          },
          {
            "label": "Otro",
            "value": "O"
          }
        ]
      },
      {
        "required": true,
        "label": "Número de Teléfono",
        "placeholder": "Ingresa tu número de teléfono",
        "name": "phone",
        "type": "PHONE"
      },
      {
        "required": true,
        "label": "Correo Electrónico",
        "placeholder": "Ingresa tu correo electrónico",
        "name": "email",
        "type": "EMAIL",
        "maxLength": 100
      },
      {
        "required": true,
        "label": "Dirección de Residencia",
        "placeholder": "Calle, ciudad, código postal",
        "name": "address",
        "type": "TEXT",
        "maxLength": 200
      },
      {
        "required": true,
        "label": "Categoría en la que desea participar",
        "placeholder": "Selecciona una categoría",
        "name": "category",
        "type": "SELECT",
        "options": [
          {
            "label": "5K",
            "value": "5k"
          },
          {
            "label": "10K",
            "value": "10k"
          },
          {
            "label": "Maratón",
            "value": "marathon"
          },
          {
            "label": "Carrera Familiar",
            "value": "family_run"
          }
        ]
      },
      {
        "required": false,
        "label": "Tamaño de camiseta",
        "placeholder": "Selecciona tu tamaño",
        "name": "shirt_size",
        "type": "SELECT",
        "options": [
          {
            "label": "S",
            "value": "S"
          },
          {
            "label": "M",
            "value": "M"
          },
          {
            "label": "L",
            "value": "L"
          },
          {
            "label": "XL",
            "value": "XL"
          }
        ]
      },
      {
        "required": false,
        "label": "Tiempo estimado",
        "placeholder": "Ingresa tu tiempo estimado",
        "name": "estimated_time",
        "type": "TEXT",
        "maxLength": 10
      },
      {
        "required": true,
        "label": "Nombre de contacto en caso de emergencia",
        "placeholder": "Persona de contacto",
        "name": "emergency_contact_name",
        "type": "TEXT",
        "maxLength": 100
      },
      {
        "required": true,
        "label": "Número de Teléfono de Emergencia",
        "placeholder": "Ingresa el número de contacto",
        "name": "emergency_contact_phone",
        "type": "PHONE"
      },
      {
        "required": false,
        "label": "Alergias o condiciones médicas relevantes",
        "placeholder": "Describe cualquier alergia o condición",
        "name": "medical_conditions",
        "type": "TEXT",
        "maxLength": 500
      },
      {
        "required": true,
        "label": "Autorización para uso de imagen",
        "placeholder": "¿Autorizas el uso de tu imagen? Sin la autorización no puedes participar del evento",
        "name": "image_consent",
        "type": "CHECKBOX"
      },
      {
        "required": true,
        "label": "Declaración de salud",
        "placeholder": "¿Estás en condiciones físicas para participar? Al aceptar estás haciendo una Declaración jurada",
        "name": "health_statement",
        "type": "CHECKBOX"
      },
      {
        "required": true,
        "label": "Exoneración de Responsabilidad",
        "placeholder": "¿Entiendes y aceptas los riesgos? se exonera a Fanki de toda responsabilidad",
        "name": "liability_waiver",
        "type": "CHECKBOX"
      },
      {
        "required": false,
        "label": "¿Cómo te enteraste de la carrera?",
        "placeholder": "Selecciona una opción",
        "name": "referral_source",
        "type": "SELECT",
        "options": [
          {
            "label": "Redes sociales",
            "value": "social_media"
          },
          {
            "label": "Amigos/Familia",
        "value": "friends_family"
          },
          {
            "label": "Carteles",
            "value": "posters"
          },
          {
            "label": "Otro",
            "value": "other"
          }
        ]
      },
      {
        "required": false,
        "label": "¿Tienes alguna preferencia sobre tu salida o grupo?",
        "placeholder": "Escribe tus preferencias",
        "name": "group_preferences",
        "type": "TEXT",
        "maxLength": 300
      },
      {
        "required": false,
        "label": "¿Estás interesado en participar en futuros eventos?",
        "placeholder": "",
        "name": "future_events",
        "type": "RADIO_GROUP",
        "options": [
          {
            "label": "Sí",
            "value": "yes"
          },
          {
            "label": "No",
            "value": "no"
          },
          {
            "label": "Tal vez",
            "value": "maybe"
          }
        ]
      }
    ]
  }
}
```

# Edición

Un evento de Inscripción puede editarse mediante el siguiente Swagger

[http://catalog-service.fankipass.svc.cluster.local/api/catalog-service/swagger-ui/index.html#/inscriptions-controller/update](http://catalog-service.fankipass.svc.cluster.local/api/catalog-service/swagger-ui/index.html#/inscriptions-controller/update)

Aquí se debe subir todo el evento nuevamente (Se puede obtener primero mediante un GET) y ajustandole los parametros que sean necesarios acomodar. Esta es la unica manera de hacer cambios en el Formulario de Inscripción.

# Formulario dinámico

Al crear un evento del tipo Inscripción se le incluye un formulario en formato JSON que permite determinar las preguntas, campos y demás componentes que el usuario debe completar al comprar la Inscripción.

## 1. Parámetros Comunes

Estos parámetros aplican a todos los tipos de campos.

**required** (booleano)  
Indica si el campo es obligatorio (`true`) u opcional (`false`).  
_Ejemplo:_ `"required": true`

**label** (cadena de texto)  
Texto que se muestra al lado del campo para describir qué información se solicita.  
_Ejemplo:_ `"label": "Nombre completo"`

**placeholder** (cadena de texto)  
Texto que aparece dentro del campo antes de que el usuario ingrese algún dato.  
_Ejemplo:_ `"placeholder": "Escribe tu nombre"`

**name** (cadena de texto)  
Identificador único del campo, utilizado para procesar y almacenar los datos ingresados.  
_Ejemplo:_ `"name": "full_name"`

**type** (cadena de texto)  
Especifica el tipo de dato o formato que debe tener el campo.  
_Ejemplo:_ `"type": "TEXT"`

**canEdit** (booleano)  
Indica si el usuario puede **editar este campo después de inscribirse**, desde la sección “Mis Órdenes” en la web o la app de Fanki.  
Mientras está en `true`, el usuario podrá modificar el valor.
Se puede obviar este campo y el sistema lo entenderá como _false_
_Ejemplo:_ `"canEdit": true`

**showInTicket** (booleano)  
Determina si el valor de este campo se mostrará en el **ticket de inscripción** (app, web o PDF).  
Cuando está en `true`, se mostrará el _label_ del campo junto con el valor o la opción seleccionada.  
Por temas de espacio en el ticket, solo se mostrarán los primero 5 campos que tengan esta opción en True. Si hay más, no se mostrarán.
Se puede obviar este campo y el sistema lo entenderá como _false_
_Ejemplo:_ `"showInTicket": true`

### 🔸 Uso especial del campo `DATE`

Si `name` = `"BIRTHDATE"`, el sistema valida que el usuario tenga **más de 18 años**.  
Si no se cumple, el formulario **no puede enviarse**.

---

## 2. Tipos de Campos Disponibles

| Tipo            | Descripción                                 | Ejemplo de uso          |
| --------------- | ------------------------------------------- | ----------------------- |
| **TEXT**        | Campo de texto libre.                       | `"type": "TEXT"`        |
| **EMAIL**       | Campo con validación de formato de email.   | `"type": "EMAIL"`       |
| **NUMBER**      | Permite solo números.                       | `"type": "NUMBER"`      |
| **DATE**        | Selector de fecha.                          | `"type": "DATE"`        |
| **SELECT**      | Menú desplegable con opciones predefinidas. | `"type": "SELECT"`      |
| **READONLY**    | Campo visible pero no editable.             | `"type": "READONLY"`    |
| **PHONE**       | Campo para teléfono con validación.         | `"type": "PHONE"`       |
| **CHECKBOX**    | Casilla de verificación sí/no.              | `"type": "CHECKBOX"`    |
| **DATETIME**    | Selección de fecha y hora.                  | `"type": "DATETIME"`    |
| **TIME**        | Selección de hora.                          | `"type": "TIME"`        |
| **FILE**        | Subida de archivos con límite de tamaño.    | `"type": "FILE"`        |
| **URL**         | Campo de direcciones web.                   | `"type": "URL"`         |
| **RADIO_GROUP** | Grupo de botones para una única opción.     | `"type": "RADIO_GROUP"` |

---

## 3. Parámetros Específicos

Algunos tipos de campo admiten configuraciones adicionales.

| Parámetro       | Tipo   | Descripción                                      | Ejemplo                         |
| --------------- | ------ | ------------------------------------------------ | ------------------------------- |
| **minLength**   | number | Mínimo de caracteres requeridos.                 | `"minLength": 3`                |
| **maxLength**   | number | Máximo de caracteres permitidos.                 | `"maxLength": 50`               |
| **options**     | array  | Lista de opciones para `SELECT` o `RADIO_GROUP`. | Ver ejemplo abajo               |
| **maxFileSize** | number | Tamaño máximo de archivo en bytes.               | `"maxFileSize": 5000000` (5 MB) |

Ejemplo de `SELECT`:

```JSON
{
  "label": "País",
  "name": "country",
  "type": "SELECT",
  "options": [
    { "label": "Argentina", "value": "AR" },
    { "label": "Chile", "value": "CL" },
    { "label": "Uruguay", "value": "UY" }
  ]
}
```

---

## 4. Validaciones

Los campos pueden incluir reglas de validación que restringen opciones según otros campos.

`"validations": [ ... ]`

---

### 4.1 Validación de Valores (dependencias entre campos)

Permite que una opción esté disponible solo si se cumple una condición en otro campo.

**Ejemplo:**

```JSON
{
  "label": "Categoría",
  "name": "category",
  "type": "SELECT",
  "options": [
    {
      "label": "Masculino",
      "value": "male_participant",
      "validations": [{ "name": "gender", "value": "M" }]
    },
    {
      "label": "Femenino",
      "value": "female_participant",
      "validations": [{ "name": "gender", "value": "F" }]
    },
    {
      "label": "Mixto",
      "value": "mixed_participant",
      "validations": [
        { "name": "gender", "value": "M" },
        { "name": "gender", "value": "F" }
      ]
    }
  ]
}

```

**Comportamiento:**

- “Masculino” solo se habilita si el campo `gender` tiene valor `"M"`.
- “Femenino” solo si `gender` = `"F"`.
- “Mixto” si cualquiera de los dos aplica.

---

### 4.2 Validación de Fechas (rango de edades)

Permite definir rangos de edad válidos en función de la fecha ingresada por el usuario.

**Ejemplo:**

```JSON
{
  "label": "Categoría",
  "name": "category",
  "type": "SELECT",
  "options": [
    {
      "label": "19-34 años",
      "value": "19_34",
      "validations": [
        {
          "name": "birthdate",
          "min": 19,
          "max": 34,
          "targetDate": "2025-12-07"
        }
      ]
    }
  ]
}

```

**Comportamiento:**

- El sistema calcula la edad del usuario comparando el campo `birthdate` con `targetDate`.
- La opción solo está disponible si el usuario tiene entre 19 y 34 años.
- Si `targetDate` no se define, se usa la **fecha actual**.

**Casos posibles:**

- Solo `min`: mayores de cierta edad.
- Solo `max`: límite superior.
- Ambos: rango de edades.

---

## 5. Ejemplo completo

```JSON
[
  {
    "required": false,
    "label": "Evento",
    "placeholder": "",
    "name": "event_name",
    "type": "READONLY"
  },
  {
    "required": true,
    "label": "Tipo de carrera",
    "placeholder": "Selecciona la distancia",
    "name": "race_type",
    "type": "SELECT",
    "options": [
      { "label": "10K", "value": "10K" },
      { "label": "21K (Media Maratón)", "value": "21K" },
      { "label": "42K (Maratón)", "value": "42K" }
    ]
  },
  {
    "required": true,
    "showInTicket": true,
    "label": "Nombre completo",
    "placeholder": "Ingresa tu nombre y apellido",
    "name": "full_name",
    "type": "TEXT",
    "minLength": 3,
    "maxLength": 120
  },
  {
    "required": true,
    "label": "Email",
    "placeholder": "tunombre@correo.com",
    "name": "email",
    "type": "EMAIL",
    "maxLength": 120
  },
  {
    "required": true,
    "label": "Teléfono",
    "placeholder": "+54 11 1234 5678",
    "name": "phone",
    "type": "PHONE"
  },
  {
    "required": true,
    "label": "Documento / Pasaporte",
    "placeholder": "Número de documento",
    "name": "document_id",
    "type": "TEXT",
    "minLength": 6,
    "maxLength": 20
  },
  {
    "required": true,
    "label": "Nacionalidad",
    "placeholder": "Selecciona tu país",
    "name": "nationality",
    "type": "SELECT",
    "options": [
      { "label": "Argentina", "value": "AR" },
      { "label": "Chile", "value": "CL" },
      { "label": "Uruguay", "value": "UY" },
      { "label": "Brasil", "value": "BR" },
      { "label": "Otro", "value": "OT" }
    ]
  },
  {
    "required": true,
    "label": "Fecha de nacimiento",
    "placeholder": "AAAA-MM-DD",
    "name": "BIRTHDATE",
    "type": "DATE"
  },
  {
    "required": true,
    "label": "Género",
    "placeholder": "Selecciona tu género",
    "name": "gender",
    "type": "SELECT",
    "options": [
      { "label": "Masculino", "value": "M" },
      { "label": "Femenino", "value": "F" },
      { "label": "No binario / X", "value": "X" }
    ]
  },
  {
    "required": true,
    "label": "Categoría",
    "placeholder": "Selecciona tu categoría",
    "name": "category",
    "type": "SELECT",
    "options": [
      {
        "label": "10K General Masculino (16+)",
        "value": "10k_m_general",
        "validations": [
          { "name": "race_type", "value": "10K" },
          { "name": "gender", "value": "M" },
          { "name": "birthdate", "min": 16, "targetDate": "2025-12-07" }
        ]
      },
      {
        "label": "10K General Femenino (16+)",
        "value": "10k_f_general",
        "validations": [
          { "name": "race_type", "value": "10K" },
          { "name": "gender", "value": "F" },
          { "name": "birthdate", "min": 16, "targetDate": "2025-12-07" }
        ]
      },
      {
        "label": "21K 18–34 Masculino",
        "value": "21k_m_18_34",
        "validations": [
          { "name": "race_type", "value": "21K" },
          { "name": "gender", "value": "M" },
          { "name": "birthdate", "min": 18, "max": 34, "targetDate": "2025-12-07" }
        ]
      },
      {
        "label": "21K 35–49 Femenino",
        "value": "21k_f_35_49",
        "validations": [
          { "name": "race_type", "value": "21K" },
          { "name": "gender", "value": "F" },
          { "name": "birthdate", "min": 35, "max": 49, "targetDate": "2025-12-07" }
        ]
      },
      {
        "label": "42K General No Binario (20+)",
        "value": "42k_x_general",
        "validations": [
          { "name": "race_type", "value": "42K" },
          { "name": "gender", "value": "X" },
          { "name": "birthdate", "min": 20, "targetDate": "2025-12-07" }
        ]
      }
    ]
  },
  {
    "required": false,
    "label": "¿Participas con silla de ruedas?",
    "placeholder": "",
    "name": "wheelchair",
    "type": "CHECKBOX"
  },
  {
    "required": true,
    "label": "Ola de largada",
    "placeholder": "Selecciona tu ola",
    "name": "start_wave",
    "type": "SELECT",
    "options": [
      { "label": "General – Ola 1 (más rápida)", "value": "wave_1" },
      { "label": "General – Ola 2", "value": "wave_2" },
      {
        "label": "Atletas en silla de ruedas",
        "value": "wave_wheelchair",
        "validations": [
          { "name": "wheelchair", "value": true }
        ]
      }
    ]
  },
  {
    "required": false,
    "label": "Marca personal (10K) en minutos",
    "placeholder": "Ej.: 52",
    "name": "pb_10k_minutes",
    "type": "NUMBER"
  },
  {
    "required": false,
    "showInTicket": true,
    "label": "Club / Equipo",
    "placeholder": "Nombre del club",
    "name": "team_name",
    "type": "TEXT",
    "maxLength": 80
  },
  {
    "required": false,
    "label": "Perfil médico (URL)",
    "placeholder": "https://...",
    "name": "medical_profile_url",
    "type": "URL"
  },
  {
    "required": true,
    "canEdit": true,
    "label": "Talle de remera",
    "placeholder": "",
    "name": "tshirt_size",
    "type": "RADIO_GROUP",
    "options": [
      { "label": "XS", "value": "XS" },
      { "label": "S", "value": "S" },
      { "label": "M", "value": "M" },
      { "label": "L", "value": "L" },
      { "label": "XL", "value": "XL" },
      { "label": "XXL", "value": "XXL" }
    ]
  },
  {
    "required": true,
    "canEdit": true,
    "label": "Turno de retiro de kit",
    "placeholder": "Selecciona día y hora",
    "name": "kit_pickup_slot",
    "type": "DATETIME"
  },
  {
    "required": false,
    "label": "Contacto de emergencia (Nombre)",
    "placeholder": "Nombre y apellido",
    "name": "emergency_contact_name",
    "type": "TEXT",
    "minLength": 3,
    "maxLength": 120
  },
  {
    "required": false,
    "label": "Contacto de emergencia (Tel.)",
    "placeholder": "+54 11 1234 5678",
    "name": "emergency_contact_phone",
    "type": "PHONE"
  },
  {
    "required": true,
    "label": "Acepto Términos y Condiciones",
    "placeholder": "",
    "name": "terms",
    "type": "CHECKBOX"
  }
]


```
