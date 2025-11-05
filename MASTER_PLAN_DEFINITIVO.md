# 🎯 MASTER PLAN DEFINITIVO: HOILAB VAPI 2.0
## LA MÁQUINA DE VENTAS IA MÁS COMPLETA PARA PERFEXCRM

**Versión:** 2.0.0
**Objetivo:** Módulo 100% funcional, sin errores, con TODAS las funcionalidades de FexCall + mejoras
**Tiempo estimado:** 14-16 horas de desarrollo concentrado
**Fecha inicio:** 5 Nov 2025

---

## 📊 ANÁLISIS COMPLETO DE FUNCIONALIDADES

### ✅ FUNCIONALIDADES DE FEXCALL A INTEGRAR (100%)

#### 1. **SISTEMA DE CAMPAÑAS**
- [x] Crear campañas de llamadas outbound
- [x] Asignar números a campañas
- [x] Programar fecha/hora de ejecución
- [x] Pausar/reanudar campañas
- [x] Ver progreso en tiempo real
- [x] Estadísticas por campaña
- [x] Retry automático de llamadas fallidas

#### 2. **PHONE NUMBERS MANAGEMENT**
- [x] Listar phone numbers de VAPI
- [x] Ver detalles de cada número
- [x] Asignar número a assistant/squad
- [x] Configurar inbound routing
- [x] Ver estadísticas de uso

#### 3. **INBOUND CALL HANDLING**
- [x] Recibir llamadas entrantes
- [x] Routing a assistant correcto
- [x] Crear lead automáticamente si no existe
- [x] Vincular a lead/customer existente
- [x] Logging de inbound calls
- [x] Webhooks para inbound

#### 4. **KNOWLEDGE BASE**
- [x] Upload de documentos (PDF, TXT, DOCX)
- [x] Crear knowledge base en VAPI
- [x] Asignar KB a assistants
- [x] Gestionar archivos
- [x] Update de contenido

#### 5. **VOICE SETTINGS**
- [x] Selección de voz (provider + voice ID)
- [x] Configurar idioma
- [x] Ajustar velocidad
- [x] Preview de voz

#### 6. **ASSISTANT BUILDER**
- [x] Crear assistants desde UI
- [x] Configurar prompt/instrucciones
- [x] Asignar tools
- [x] Asignar knowledge base
- [x] Configurar voz
- [x] Test de assistant

#### 7. **CALL LOGS AVANZADO**
- [x] Estadísticas (Inbound/Outbound/Hoy/Ayer)
- [x] Reproductor de audio
- [x] Transcripciones formateadas
- [x] Modal de detalles completo
- [x] Copy to clipboard
- [x] Filtros avanzados
- [x] Export a CSV

#### 8. **DASHBOARD COMPLETO**
- [x] KPIs principales
- [x] Gráficos de actividad
- [x] Conversion funnel
- [x] Revenue tracking
- [x] Cost per lead

---

### 🚀 FUNCIONALIDADES NUEVAS (MEJORAS HOILAB)

#### 9. **INTEGRACIÓN TOTAL PERFEXCRM**
- [x] Lead → Customer (conversión automática)
- [x] Auto-crear Estimates con items
- [x] Auto-crear Invoices
- [x] Auto-crear Contracts
- [x] Auto-crear Projects post-venta
- [x] Auto-crear Tasks de seguimiento
- [x] Sync con CRM status

#### 10. **SQUADS AVANZADO**
- [x] Multi-assistant squads
- [x] Sector/industria por squad
- [x] Asignar squad por lead source
- [x] Rotation de asistentes
- [x] Escalation logic

#### 11. **AUTOMATIZACIÓN INTELIGENTE**
- [x] Lead scoring dinámico
- [x] Flows HOT/WARM/COLD
- [x] Follow-ups automáticos
- [x] Retry inteligente
- [x] Nurture sequences
- [x] A/B testing de scripts

#### 12. **ANALYTICS AVANZADO**
- [x] ROI calculator
- [x] Attribution tracking
- [x] Comparative analytics
- [x] Forecasting
- [x] Heatmaps de llamadas
- [x] Best time to call

#### 13. **NOTIFICACIONES Y ALERTAS**
- [x] Real-time notifications
- [x] Email digests
- [x] SMS alerts (opcional)
- [x] Slack/Teams webhooks
- [x] Custom triggers

---

## 🏗️ ARQUITECTURA TÉCNICA

### BASE DE DATOS (12 tablas)

```sql
1. hoilab_vapi_squads
2. hoilab_vapi_assistants  
3. hoilab_vapi_phone_numbers
4. hoilab_vapi_campaigns
5. hoilab_vapi_campaign_numbers
6. hoilab_vapi_call_queue
7. hoilab_vapi_call_logs (extender alm_call_logs)
8. hoilab_vapi_follow_ups
9. hoilab_vapi_budgets_auto
10. hoilab_vapi_contracts_auto
11. hoilab_vapi_knowledge_bases
12. hoilab_vapi_automation_log
```

### CONTROLADORES (10 archivos)

```
1. Hoilab_vapi.php (main)
2. Squads.php
3. Assistants.php
4. Phone_numbers.php
5. Campaigns.php
6. Call_logs.php
7. Analytics.php
8. Knowledge_base.php
9. Settings.php
10. Webhooks.php
```

### MODELOS (1 archivo principal + helpers)

```
1. Hoilab_vapi_model.php (core - 2000+ líneas)
```

### LIBRERÍAS (2 archivos)

```
1. Hoilab_vapi_api.php (VAPI API wrapper)
2. Hoilab_vapi_crm.php (PerfexCRM integration)
```

### VISTAS (25+ archivos)

```
Squads/
  - manage.php
  - view.php
  - create.php
  
Assistants/
  - manage.php
  - create.php
  - builder.php
  
Phone_numbers/
  - manage.php
  - assign.php
  
Campaigns/
  - manage.php
  - create.php
  - view.php
  - stats.php
  
Call_logs/
  - manage.php
  - modals/detail.php
  
Analytics/
  - dashboard.php
  - reports.php
  
Knowledge_base/
  - manage.php
  - create.php
  
Settings/
  - tabs/basic.php
  - tabs/automation.php
  - tabs/webhooks.php
  - tabs/advanced.php
  
Lead/
  - tab_content.php
  
Customer/
  - tab_content.php
```

---

## 📋 PLAN DE EJECUCIÓN DETALLADO

### FASE 1: PREPARACIÓN Y ANÁLISIS (1 hora)
**Objetivo:** Entender completamente FexCall y preparar ambiente

**Tareas:**
1. [30min] Análisis exhaustivo de FexCall
   - Leer Ai_lead_manager.php completo
   - Leer Call_logs_model.php
   - Leer Campaigns_model.php
   - Analizar vistas principales
   - Listar TODAS las funcionalidades

2. [15min] Extraer código útil de FexCall
   - Copiar funciones de campaigns
   - Copiar sistema de phone numbers
   - Copiar knowledge base management
   - Copiar assistant builder

3. [15min] Crear estructura de directorios limpia
   - Reorganizar carpetas
   - Preparar archivos nuevos
   - Eliminar archivos sobrantes

---

### FASE 2: MIGRACIÓN DE BASE DE DATOS (1.5 horas)
**Objetivo:** BD completa y funcional

**Tareas:**
1. [30min] Crear migración 201 - Phone Numbers
```sql
CREATE TABLE hoilab_vapi_phone_numbers (
  id INT AUTO_INCREMENT PRIMARY KEY,
  vapi_phone_id VARCHAR(255) UNIQUE,
  number VARCHAR(50),
  provider VARCHAR(50),
  assigned_to_type ENUM('squad','assistant'),
  assigned_to_id INT,
  is_active TINYINT(1) DEFAULT 1,
  inbound_enabled TINYINT(1) DEFAULT 1,
  last_sync_at DATETIME,
  created_at DATETIME
);
```

2. [20min] Crear migración 202 - Campaigns
```sql
CREATE TABLE hoilab_vapi_campaigns (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(255),
  squad_id INT,
  status ENUM('draft','scheduled','running','paused','completed'),
  total_leads INT DEFAULT 0,
  called_leads INT DEFAULT 0,
  scheduled_at DATETIME,
  started_at DATETIME,
  completed_at DATETIME,
  settings JSON,
  created_at DATETIME
);

CREATE TABLE hoilab_vapi_campaign_numbers (
  id INT AUTO_INCREMENT PRIMARY KEY,
  campaign_id INT,
  lead_id INT,
  status ENUM('pending','calling','completed','failed'),
  call_log_id INT,
  attempts INT DEFAULT 0,
  created_at DATETIME
);
```

3. [20min] Crear migración 203 - Knowledge Base
```sql
CREATE TABLE hoilab_vapi_knowledge_bases (
  id INT AUTO_INCREMENT PRIMARY KEY,
  vapi_kb_id VARCHAR(255) UNIQUE,
  name VARCHAR(255),
  description TEXT,
  squad_id INT,
  files_count INT DEFAULT 0,
  last_sync_at DATETIME,
  created_at DATETIME
);
```

4. [20min] Crear migración 204 - Contracts Auto
```sql
CREATE TABLE hoilab_vapi_contracts_auto (
  id INT AUTO_INCREMENT PRIMARY KEY,
  lead_id INT,
  customer_id INT,
  contract_id INT,
  call_log_id INT,
  template_id INT,
  status ENUM('pending','sent','signed','rejected'),
  sent_at DATETIME,
  signed_at DATETIME,
  created_at DATETIME
);
```

5. [20min] Actualizar migración 200 - Mejoras
   - Añadir campos faltantes
   - Indices optimizados
   - Foreign keys

---

### FASE 3: MODELO PRINCIPAL (2.5 horas)
**Objetivo:** Hoilab_vapi_model.php completo con TODA la lógica

**Tareas:**
1. [30min] Phone Numbers Management
```php
// Métodos:
- get_phone_numbers()
- sync_phone_numbers_from_vapi()
- assign_phone_number($number_id, $type, $id)
- get_phone_stats($number_id)
- configure_inbound($number_id, $settings)
```

2. [45min] Campaigns System
```php
// Métodos:
- create_campaign($data)
- add_leads_to_campaign($campaign_id, $lead_ids)
- start_campaign($campaign_id)
- pause_campaign($campaign_id)
- process_campaign_queue($campaign_id)
- get_campaign_stats($campaign_id)
```

3. [30min] Knowledge Base Management
```php
// Métodos:
- create_knowledge_base($data)
- upload_file_to_kb($kb_id, $file)
- sync_knowledge_bases()
- assign_kb_to_squad($kb_id, $squad_id)
```

4. [30min] Integración PerfexCRM Avanzada
```php
// Métodos:
- convert_lead_to_customer($lead_id, $call_log_id)
- create_contract_from_template($customer_id, $template_id)
- create_project_post_sale($customer_id, $contract_id)
- create_follow_up_tasks($customer_id, $type)
```

5. [15min] Inbound Call Handling
```php
// Métodos:
- handle_inbound_call($data)
- find_or_create_lead_by_phone($phone)
- route_to_assistant($call_data)
```

6. [20min] Analytics Avanzado
```php
// Métodos:
- get_roi_metrics($date_range)
- get_attribution_data()
- get_call_heatmap()
- get_best_time_to_call()
- forecast_conversions($period)
```

---

### FASE 4: LIBRERÍA VAPI API EXTENDIDA (1 hora)
**Objetivo:** Wrapper completo de VAPI API

**Tareas:**
1. [15min] Phone Numbers endpoints
```php
- get_phone_numbers()
- get_phone_number($id)
- update_phone_number($id, $data)
- buy_phone_number($data)
```

2. [15min] Knowledge Base endpoints
```php
- get_knowledge_bases()
- create_knowledge_base($data)
- upload_file($kb_id, $file)
- delete_file($kb_id, $file_id)
```

3. [15min] Voice endpoints
```php
- get_voices()
- get_voice($id)
```

4. [15min] Mejorar error handling
   - Retry logic
   - Rate limiting
   - Logging detallado

---

### FASE 5: CONTROLADORES (3 horas)
**Objetivo:** UI completa y funcional

**Tareas:**
1. [30min] Squads.php + Assistants.php
   - CRUD completo
   - Builder de assistants
   - Asignar tools
   - Asignar KB

2. [30min] Phone_numbers.php
   - Listar números
   - Sync desde VAPI
   - Asignar a squad/assistant
   - Configurar inbound
   - Ver estadísticas

3. [45min] Campaigns.php
   - Crear campaña
   - Añadir leads
   - Configurar settings
   - Start/Pause/Stop
   - Ver progreso
   - Estadísticas

4. [30min] Call_logs.php
   - Listar con stats
   - Filtros avanzados
   - Modal de detalles
   - Export CSV

5. [30min] Analytics.php
   - Dashboard completo
   - Reports
   - Charts
   - ROI calculator

6. [15min] Knowledge_base.php
   - CRUD de KB
   - Upload files
   - Asignar a squads

7. [30min] Settings.php
   - 4 tabs organizados
   - Test connection
   - Webhooks URLs
   - Validaciones

---

### FASE 6: VISTAS (4 horas)
**Objetivo:** UI profesional y completa

**Tareas:**
1. [45min] Squads + Assistants views
   - Manage (lista con stats)
   - View (detalles + asistentes)
   - Create/Edit (form completo)
   - Builder (UI para crear assistant)

2. [30min] Phone Numbers views
   - Manage (tabla con stats)
   - Assign (modal)
   - Configure (modal para inbound)

3. [45min] Campaigns views
   - Manage (lista con stats)
   - Create (wizard paso a paso)
   - View (progreso en tiempo real)
   - Stats (dashboard específico)

4. [45min] Call Logs views
   - Manage (tabla con filtros + stats header)
   - Modal detail (tabs: Details, Summary, Transcripts)
   - Reproductor de audio
   - Transcripts formateados

5. [30min] Analytics views
   - Dashboard (KPIs + charts)
   - Reports (filtros + export)
   - ROI calculator

6. [30min] Knowledge Base views
   - Manage
   - Create/Edit
   - File uploader

7. [30min] Settings view
   - 4 tabs bien diseñados
   - Validaciones en front
   - Test buttons

8. [15min] Lead/Customer tabs
   - Historial de llamadas
   - Info de automatización
   - Botones de acción

---

### FASE 7: ASSETS (1.5 horas)
**Objetivo:** JS y CSS completos

**Tareas:**
1. [45min] JavaScript (hoilab_vapi.js)
```javascript
// Funciones principales:
- hoilab_copy_to_clipboard()
- hoilab_open_call_detail()
- hoilab_load_lead_calls()
- hoilab_initiate_manual_call()
- hoilab_start_campaign()
- hoilab_pause_campaign()
- hoilab_sync_phone_numbers()
- hoilab_test_api_connection()
- hoilab_upload_kb_file()
- hoilab_play_recording()
- hoilab_render_transcripts()
```

2. [30min] CSS (hoilab_vapi.css)
```css
/* Estilos para:
- Temperature badges
- Score badges
- Stats widgets
- Transcripts chat
- Campaign progress bars
- Charts containers
- Modal styling
- Forms
- Tables
*/
```

3. [15min] Copy assets útiles de FexCall
   - Verificar templates.js (si es útil)
   - Adaptar estilos existentes

---

### FASE 8: WEBHOOKS Y TOOLS (1.5 horas)
**Objetivo:** Webhooks completos para IN/OUT

**Tareas:**
1. [30min] Webhook Inbound
```php
public function vapi_inbound_call() {
    // Recibir llamada entrante
    // Identificar número
    // Buscar/crear lead
    // Vincular a CRM
    // Log
}
```

2. [30min] Webhook Call Status
```php
public function vapi_call_status() {
    // Actualizar estado en tiempo real
    // Notify UI vía websocket/polling
}
```

3. [15min] Tools adicionales
```php
- convert_to_customer
- create_contract
- schedule_follow_up_task
```

4. [15min] Mejorar seguridad
   - Validar firma de webhook
   - Rate limiting
   - IP whitelist (opcional)

---

### FASE 9: INTEGRACIONES PERFEXCRM (2 horas)
**Objetivo:** Integración total con entidades PerfexCRM

**Tareas:**
1. [30min] Lead → Customer
```php
- Validar datos completos
- Crear customer
- Migrar custom fields
- Crear contact
- Vincular calls
- Update lead status
```

2. [30min] Auto Estimates
```php
- Templates de productos
- Cálculo de precios
- Items configurables
- Términos y condiciones
- Email automático
```

3. [20min] Auto Contracts
```php
- Seleccionar template
- Merge fields
- Enviar para firma
- Tracking de status
```

4. [20min] Auto Projects
```php
- Crear proyecto post-venta
- Asignar tareas
- Set milestones
- Notify equipo
```

5. [20min] Tasks automáticas
```php
- Follow-up tasks
- Reminder tasks
- Escalation tasks
```

---

### FASE 10: AUTOMATIZACIÓN AVANZADA (1.5 horas)
**Objetivo:** Flows inteligentes

**Tareas:**
1. [30min] Lead Scoring Dinámico
```php
- Scoring rules engine
- Update score on events
- Thresholds configurables
- Automatic routing
```

2. [30min] A/B Testing
```php
- Multiple scripts por squad
- Random assignment
- Track results
- Auto-select winner
```

3. [30min] Nurture Sequences
```php
- Multi-touch sequences
- Email + Call + SMS
- Pause on engagement
- Auto-complete on conversion
```

---

### FASE 11: TESTING COMPLETO (3 horas)
**Objetivo:** Garantizar 100% funcional

**Tareas:**
1. [30min] Testing de Instalación
   - Fresh install
   - Migraciones
   - Settings defaults
   - Menús y permisos

2. [30min] Testing de Squads & Assistants
   - Sync desde VAPI
   - Crear squad
   - Asignar asistentes
   - Set default

3. [30min] Testing de Campaigns
   - Crear campaña
   - Añadir leads
   - Iniciar
   - Pausar
   - Ver stats
   - Reintentos

4. [20min] Testing de Phone Numbers
   - Sync
   - Asignar
   - Inbound call
   - Stats

5. [20min] Testing de Call Logs
   - Ver lista
   - Abrir modal
   - Reproducir audio
   - Ver transcripts
   - Export CSV

6. [20min] Testing de Webhooks
   - Call completed (outbound)
   - Inbound call
   - Call status updates
   - Tools calls

7. [20min] Testing de Automatización
   - Lead scoring
   - HOT flow
   - WARM flow
   - COLD flow
   - Follow-ups

8. [20min] Testing de Integraciones CRM
   - Lead → Customer
   - Auto estimate
   - Auto contract
   - Auto project
   - Tasks

9. [30min] Testing de Performance
   - 100 leads en campaña
   - 500 call logs
   - Queries optimization
   - Load times

---

### FASE 12: DOCUMENTACIÓN (1 hora)
**Objetivo:** Documentación completa y profesional

**Tareas:**
1. [15min] README.md actualizado
   - Todas las funcionalidades
   - Screenshots
   - Requirements

2. [15min] INSTALLATION_GUIDE.md
   - Paso a paso detallado
   - Troubleshooting

3. [10min] USER_GUIDE.md
   - Cómo usar cada función
   - Best practices

4. [10min] API_DOCUMENTATION.md
   - Endpoints
   - Webhooks
   - Tools

5. [10min] CHANGELOG.md
   - v2.0.0 features
   - Breaking changes
   - Migration guide

---

## ⏱️ CRONOGRAMA

### DÍA 1 (8 horas)
- **09:00-10:00** Fase 1: Preparación
- **10:00-11:30** Fase 2: Migraciones BD
- **11:30-14:00** Fase 3: Modelo Principal
- **14:00-15:00** BREAK
- **15:00-16:00** Fase 4: Librería VAPI
- **16:00-19:00** Fase 5: Controladores

### DÍA 2 (8 horas)
- **09:00-13:00** Fase 6: Vistas
- **13:00-14:00** BREAK
- **14:00-15:30** Fase 7: Assets
- **15:30-17:00** Fase 8: Webhooks
- **17:00-19:00** Fase 9: Integraciones CRM

### DÍA 3 (4 horas)
- **09:00-10:30** Fase 10: Automatización
- **10:30-13:30** Fase 11: Testing
- **13:30-14:30** Fase 12: Documentación

**TOTAL: 20 horas** (distribución flexible según progreso)

---

## ✅ CRITERIOS DE ÉXITO

El módulo estará 100% completo cuando:

1. ✅ Se instala sin errores
2. ✅ Todas las migraciones funcionan
3. ✅ Sync de squads funciona
4. ✅ Llamadas outbound funcionan
5. ✅ Llamadas inbound funcionan
6. ✅ Campañas funcionan end-to-end
7. ✅ Phone numbers se gestionan
8. ✅ Knowledge base funciona
9. ✅ Call logs muestran todo correctamente
10. ✅ Analytics muestra datos reales
11. ✅ Lead → Customer funciona
12. ✅ Auto estimates funcionan
13. ✅ Auto contracts funcionan
14. ✅ Webhooks responden correctamente
15. ✅ Tools de VAPI funcionan
16. ✅ UI es responsive y profesional
17. ✅ Performance es óptima
18. ✅ No hay archivos sobrantes
19. ✅ Documentación está completa
20. ✅ Testing 100% pass

---

## 🚀 INICIO INMEDIATO

**Estoy listo para empezar.**

Confirma y comienzo con FASE 1 inmediatamente.

