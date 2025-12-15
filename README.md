# DIAGNÓSTICO TÉCNICO-FUNCIONAL DEL SISTEMA ACTUAL

Este documento describe el funcionamiento del sistema actual, detalla las responsabilidades de cada módulo e identifica las deficiencias técnicas y funcionales que afectan la operación. El análisis justifica la necesidad de migrar hacia un nuevo sistema integral.

---

## 1. MÓDULO: GESTIÓN DE USUARIOS

### 1.1 Submenú: Usuarios del Sistema

**Descripción**
Administra a las personas autorizadas a operar el sistema (Presidente, Secretaria, Tesorero y personal técnico). Permite la creación de cuentas y el acceso a las funcionalidades del sistema.

**Deficiencias**

* **Roles indefinidos:** Todos los usuarios operan con permisos de administrador, lo que elimina la segregación de funciones y permite acciones no autorizadas entre áreas.

---

## 2. MÓDULO: TRÁMITES Y SERVICIOS (FUT)

**Descripción general**
El Formato Único de Trámite (FUT) centraliza la recepción, seguimiento y atención de solicitudes administrativas de usuarios externos, funcionando como ventanilla única.

### 2.1 Submenú: Tipo de Solicitud

**Descripción**
Permite definir y parametrizar los trámites disponibles (nuevas conexiones, cambios de nombre, reclamos), estableciendo su clasificación dentro del sistema.

### 2.2 Submenú: Tipo de Documentos

**Descripción**
Gestiona el catálogo de requisitos documentarios exigidos por cada tipo de trámite.

**Deficiencias críticas**

* **Falta de validación dinámica:** No admite reglas de negocio (obligatoriedad condicional), quedando la verificación sujeta al criterio del operador.

### 2.3 Submenú: Impresión

**Descripción**
Genera el documento FUT en formato PDF para su firma física por el solicitante.

### 2.4 Submenú: Registrar / Actualizar

**Descripción**
Interfaz de Mesa de Partes para la recepción de expedientes, verificación básica de requisitos y registro oficial del inicio del trámite.

### 2.5 Submenú: Reportes

**Descripción**
Proporciona estadísticas sobre el volumen y tipo de trámites atendidos por periodo, apoyando la toma de decisiones.

---

## 3. MÓDULO: CONTRATOS

**Descripción general**
Formaliza el vínculo legal entre la entidad y el usuario, administrando el ciclo de vida del contrato de suministro de agua potable.

### 3.1 Submenú: Tipo de Sector

**Descripción**
Configura las categorías tarifarias (Doméstico, Comercial, Estatal, Social) y su estructura de costos.

**Deficiencias críticas**

* **Vulnerabilidad de tarifas:** La modificación de parámetros carece de auditoría y niveles de aprobación.

### 3.2 Submenú: Tipo de Cliente

**Descripción**
Define la clasificación administrativa del usuario (propietario, inquilino, persona jurídica) para la correcta asignación de responsabilidades.

### 3.3 Submenú: Importe de Instalación

**Descripción**
Establece los costos iniciales asociados a la suscripción de nuevos contratos.

### 3.4 Submenú: Registrar / Actualizar

**Descripción**
Crea y mantiene la ficha contractual, vinculando usuario, predio y tarifa.

**Deficiencias críticas**

* **Contratos a morosos:** Se permite la generación de contratos con deudas pendientes.
* **Falta de validación predial:** Posibilidad de múltiples contratos activos para un mismo predio.

### 3.5 Submenú: Reportes

**Descripción**
Genera listados del padrón de contratos por estado.

**Deficiencias críticas**

* **Inconsistencia de datos:** Discrepancias entre el estado visualizado y el registrado en base de datos.

---

## 4. MÓDULO: SUMINISTROS

**Descripción general**
Gestiona el parque de medidores y el historial técnico de los puntos de suministro.

### 4.1 Submenú: Medidor de Agua / Buscar

**Descripción**
Permite la consulta del inventario de medidores mediante criterios de búsqueda.

**Deficiencias críticas**

* **Búsqueda lenta:** Tiempos de respuesta elevados por falta de indexación adecuada.

### 4.2 Submenú: Actualizar Tipo de Cliente

**Descripción**
Permite la recategorización de usuarios según el uso del predio.

### 4.3 Submenú: Actualizar Medidor

**Descripción**
Registra el reemplazo o mantenimiento de medidores, asegurando continuidad en la medición.

---

## 5. MÓDULO: FINANZAS Y CAJA – COBROS

**Descripción general**
Gestiona el ciclo comercial completo: configuración de cobros, lectura de consumos, facturación y recaudación.

### 5.1 Submenú: Configuración Tipo de Cobro

**Descripción**
Define los conceptos facturables y sus reglas de cálculo.

### 5.2 Submenú: Configuración Día Máximo

**Descripción**
Establece fechas límite de pago para evitar moras o cortes.

**Deficiencias críticas**

* **Fechas manuales:** El cierre de ciclo no es automático y depende de intervención humana.

### 5.3 Submenú: Registrar Lectura

**Descripción**
Permite la digitación masiva de lecturas de medidores.

### 5.4 Submenú: Registrar Cobros (Generación de Deuda)

**Descripción**
Calcula consumos y genera recibos de facturación.

### 5.5 Submenú: Impresión de Recibos / Historial

**Descripción**
Gestiona la emisión y reimpresión de recibos.

### 5.6 Submenú: Cobrar

**Descripción**
Registra pagos y actualiza el estado de cuenta del usuario.

### 5.7 Submenú: Anular

**Descripción**
Permite revertir operaciones de cobro erróneas.

---

## 6. MÓDULO: EGRESOS

**Descripción general**
Registra y controla los gastos operativos y administrativos.

### 6.1 Submenú: Configuración de Conceptos

**Descripción**
Clasifica los tipos de gastos.

### 6.2 Submenú: Registrar Egreso

**Descripción**
Registra cada salida de dinero con su detalle.

### 6.3 Submenú: Anular Egreso

**Descripción**
Cancela registros incorrectos para corregir saldos.

---

## 7. MÓDULO: FLUJO DE CAJA

**Descripción general**
Controla la tesorería diaria mediante apertura y cierre de caja.

### 7.1 Submenú: Configuración

**Descripción**
Parámetros iniciales del funcionamiento de caja.

### 7.2 Submenú: Apertura

**Descripción**
Registra el saldo inicial de la jornada.

### 7.3 Submenú: Cierre

**Descripción**
Consolida ingresos y egresos del día.

**Deficiencias críticas**

* **Cierres inexactos:** Mezcla de efectivo con otros medios de pago.

### 7.4 Submenú: Estado

**Descripción**
Muestra el balance de caja.

**Deficiencias críticas**

* **Caja ciega:** No existe visualización confiable en tiempo real.

---

## 8. MÓDULO: BALANCE GENERAL

**Descripción general**
Provee una visión consolidada de la situación financiera.

### 8.1 Submenú: Consolidado Anual

**Descripción**
Resumen del desempeño financiero anual.

### 8.2 Submenú: Consolidado Mensual

**Descripción**
Detalle mensual de ingresos y egresos para el análisis de tendencias.
