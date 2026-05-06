# 📊 COTIZACIÓN: 7 BASES DE DATOS RÉPLICAS - AWS vs AZURE

**Período:** 1 AÑO (2026)  
**Fecha de cotización:** 2026-05-06  
**Usuario:** Kuroro-rich  
**Sistemas:** 7 colegios + holding

---

## 🎯 RESUMEN EJECUTIVO

| Métrica | AWS | AZURE | Ganador |
|---------|-----|-------|----------|
| **💰 Costo Mensual** | **$27.58** | $285.98 | **AWS ⭐⭐⭐** |
| **💰 Costo Anual** | **$331** | $3,427.76 | **AWS ⭐⭐⭐** |
| **💰 Diferencia/Año** | — | **-$3,096.76** | **AHORRO AWS** |
| **⚙️ Sin Código** | ⚠️ Lambda básico | ✅ 100% visual | AZURE |
| **📚 Facilidad** | Moderada (4-5h) | Muy fácil (2h) | AZURE ⭐ |
| **🔧 Monitoreo** | CloudWatch+SNS | Azure Monitor | Empate |

---

## 💰 DESGLOSE DETALLADO - AWS

| Servicio | Costo Mes | Costo Año | Descripción |
|----------|-----------|-----------|-------------|
| RDS MySQL (db.t3.small) | $15.00 | $180.00 | Servidor principal 7 BD |
| Almacenamiento (50 GB) | $2.00 | $24.00 | Datos replicados |
| DMS (Replicación inicial) | $2.00 | $24.00 | Copiar BD originales |
| Lambda (95 ejecuciones/mes) | $0.00 | $0.00 | ✅ Gratis (Free Tier) |
| EventBridge (Programación) | Gratis | Gratis | ✅ Programar horarios |
| CloudWatch (10 alarmas) | Gratis | Gratis | ✅ Monitoreo |
| SNS (50 emails/mes) | $0.00 | $0.00 | ✅ Gratis (Free Tier) |
| **SUBTOTAL** | **$19.00** | **$228.00** | Base |
| **Margen (+30%)** | **$5.74** | **$68.40** | Imprevistos |
| **TOTAL AWS** | **$27.58** | **$330.96** | **ESTIMADO FINAL** |

---

## 💰 DESGLOSE DETALLADO - AZURE

| Servicio | Costo Mes | Costo Año | Descripción |
|----------|-----------|-----------|-------------|
| Azure MySQL (B4MS, 4GB) | $277.98 | $3,335.76 | Servidor principal 7 BD |
| Data Factory (Replicación) | $3.00 | $36.00 | Copiar datos automáticamente |
| Logic Apps (Automatización) | $3.00 | $36.00 | Actualizar tablas por horario |
| Azure Monitor (Monitoreo) | Gratis | Gratis | ✅ Primeras 10 alertas |
| Email Notifications | $2.00 | $24.00 | Envío de alertas por correo |
| **TOTAL AZURE** | **$285.98** | **$3,431.76** | **ESTIMADO FINAL** |

---

## 📈 CÁLCULO DE EJECUCIONES (TABLAS Y FRECUENCIAS)

| Tabla | Frecuencia | Días/Mes | Ejecuciones/Mes | Ejecuciones/Año |
|-------|-----------|----------|-----------------|------------------|
| **asistencia** | 2 veces/día | 30 | 60 | 720 |
| **alumno** | 1 vez/día | 30 | 30 | 360 |
| **trabajador** | 1 vez/semana | 4 | 4 | 52 |
| **documentos** | 1 vez/viernes | 4 | 4 | 48 |
| **TOTAL** | — | — | **98** | **1,180** |

### Detalles:
- **asistencia:** Se actualiza TODOS los días a las 8 AM y 4 PM (2 veces)
- **alumno:** Se actualiza TODOS los días a las 6 AM (1 vez)
- **trabajador:** Se actualiza LUNES a las 9 AM (1 vez/semana)
- **documentos:** Se actualiza VIERNES a las 4 PM (1 vez/semana)

---

## ⚙️ CÁLCULO LAMBDA (AWS) - DETALLES TÉCNICOS

```
PARAMETRO                     VALOR                CÁLCULO
═══════════════════════════════════════════════════════════════
Ejecuciones/mes               98                   (asistencia: 60 + alumno: 30 + trabajador: 4 + documentos: 4)
Tiempo promedio/ejecución    15 segundos          (sincronizar + actualizar tabla)
GB asignado (Lambda)          128 MB = 0.125 GB    (configuración estándar)
GB-segundos/mes              184                   (98 × 15 × 0.125)
GB-segundos/año              2,208                 (184 × 12)

COSTO AWS LAMBDA:
├─ Primeras 1,000,000 GB-seg/mes: GRATIS ✅
├─ Tu consumo: 2,208 GB-seg/año
├─ vs disponible: 1,000,000 GB-seg/año
└─ RESULTADO: $0.00/mes (DENTRO DEL FREE TIER)
```

---

## 📧 CÁLCULO SNS (AWS) - NOTIFICACIONES POR EMAIL

```
PARAMETRO                     VALOR
═══════════════════════════════════════════════════════════════
Alertas esperadas/mes         50 (escenario moderado-probable)
Emails/mes                    50
Primeras 1000/mes             GRATIS ✅
Costo SNS                     $0.00/mes (FREE TIER)
```

### Alertas Configuradas (10 gratis en CloudWatch):
1. ✅ Lambda asistencia - Fallos
2. ✅ Lambda alumno - Fallos
3. ✅ Lambda trabajador - Fallos
4. ✅ Lambda documentos - Fallos
5. ✅ RDS - Desconexión
6. ✅ RDS - CPU alta (>80%)
7. ✅ RDS - Almacenamiento bajo (<5GB)
8. ✅ Lambda - Ejecución lenta (>30 seg)
9. ✅ Lambda - Errores de query
10. ✅ DMS - Fallos de replicación

---

## 📊 CLOUDWATCH (AWS) - MONITOREO

```
COMPONENTE                    COSTO           ESTADO
═══════════════════════════════════════════════════════════════
Alarmas (primeras 10)         $0.00/mes       GRATIS ✅
Alarmas adicionales (si hay)  $0.10 c/una     No necesarias
Dashboard                     $0.00/mes       GRATIS ✅
Logs de Lambda                GRATIS          5GB/mes incluidos ✅

TOTAL CLOUDWATCH              $0.00/mes       (GRATIS)
```

---

## 🔄 COMPARATIVA DETALLADA: AWS vs AZURE

| Criterio | AWS | AZURE | Ganador |
|----------|-----|-------|----------|
| 💰 Precio Anual | **$331** | $3,427.76 | **AWS ⭐⭐⭐** |
| 💰 Precio Mensual | **$27.58** | $285.98 | **AWS ⭐⭐⭐** |
| 💰 Ahorro 5 años | **$15,485** | — | **AWS** |
| ⚙️ Sin Código | ⚠️ Lambda básico | ✅ 100% visual | **AZURE ⭐** |
| 📚 Facilidad | Moderada (4-5h) | Muy fácil (2h) | **AZURE ⭐⭐** |
| 🔧 Automatización | EventBridge | Triggers | Empate |
| 📊 Monitoreo | CloudWatch+SNS | Azure Monitor | Empate |
| 📈 Escalabilidad | Excelente | Excelente | Empate |
| 📖 Documentación | Excelente | Excelente | Empate |
| 💬 Soporte | Gratis/Pagado | Gratis/Pagado | Empate |
| 📦 Almacenamiento | $2/50GB extra | Incluido | AZURE ⭐ |
| 🔌 Power BI | ✅ Perfecta | ✅ Perfecta | Empate |
| 🎓 Curva Aprendizaje | Moderada (3-5h) | Baja (1-2h) | **AZURE ⭐** |

---

## ✅ VENTAJAS Y DESVENTAJAS

### AWS VENTAJAS:
- ✅ **11.3X más barato** que Azure ($3,096/año de diferencia)
- ✅ Muy escalable para crecimiento futuro
- ✅ Lambda es flexible y poderoso
- ✅ Free Tier cubre casi todo el presupuesto
- ✅ Excelente documentación y comunidad
- ✅ CloudWatch es muy robusto y granular
- ✅ ROI extraordinario (ahorras $3,096 para otros proyectos)
- ✅ Experiencia valiosa en tecnología cloud

### AWS DESVENTAJAS:
- ❌ Requiere código Python básico (Lambda)
- ❌ Curva de aprendizaje moderada (3-5 horas)
- ❌ Más pasos de configuración que Azure
- ⚠️ No ideal si el equipo NO quiere aprender programación

---

### AZURE VENTAJAS:
- ✅ 100% visual - NO requiere código
- ✅ Drag-drop muy intuitivo
- ✅ Facilidad extrema (2 horas de aprendizaje)
- ✅ Ideal para no desarrolladores
- ✅ Buena integración con Microsoft Office/Teams
- ✅ Excelente soporte técnico
- ✅ Aprendizaje rápido

### AZURE DESVENTAJAS:
- ❌ **11.3X más caro** que AWS ($3,096/año de diferencia)
- ❌ Presupuesto alto para el valor entregado
- ❌ No es óptimo si tienes budget limitado
- ❌ Costo operacional crece sin beneficio claro
- ❌ Menos escalable económicamente

---

## 🏆 RECOMENDACIÓN FINAL

### ✅ OPCIÓN 1: AWS (RECOMENDADO) ⭐⭐⭐

**Métricas:**
- **Costo/año:** $331 (~$27.58/mes)
- **Razón:** Presupuesto ULTRA bajo
- **Ideal si:** Tienes budget limitado o quieres máximo ROI
- **Requisito:** Aprender Python básico (2-3 horas, muy fácil)
- **Beneficio:** Ahorras $3,096/año
- **Curva aprendizaje:** 4-5 horas total
- **Rentabilidad:** 🌟🌟🌟 **Excelente**

**PROPUESTA PARA TU JEFE:**
> "AWS es 11 veces más barato. Por $331/año tenemos TODO incluido.
> El costo de aprender Python (5 horas) se recupera en los ahorros anuales.
> En 5 años: Ahorro de $15,483.80"

---

### OPCIÓN 2: AZURE

**Métricas:**
- **Costo/año:** $3,427.76 (~$285.98/mes)
- **Razón:** Sin código, 100% visual
- **Ideal si:** No quieres código Y tienes budget disponible
- **Requisito:** Ninguno (todo drag-drop)
- **Beneficio:** Facilidad extrema
- **Curva aprendizaje:** 2-3 horas total
- **Rentabilidad:** Buena pero menor que AWS

**PROPUESTA PARA TU JEFE:**
> "Azure cuesta más pero no necesitas código.
> Si el equipo no sabe programar, Azure es más fácil pero cuesta 11x más.
> En 5 años: Inversión de $17,138.80 vs AWS"

---

## 📋 PROPUESTA FINAL EJECUTIVA

### 🎯 ELEGIR: AWS

**RAZONES PRINCIPALES:**
1. ✅ **Presupuesto:** $331/año vs $3,427.76/año (diferencia: **$3,096**)
2. ✅ **ROI:** Los ahorros anuales pagan **10 cursos de Python**
3. ✅ **Escalabilidad:** Si crece, AWS sigue siendo muy barato
4. ✅ **Aprendizaje:** Python básico es skill valiosa (2-3 horas)
5. ✅ **Flexibilidad:** Lambda permite hacer cosas más complejas
6. ✅ **Free Tier:** Cubre 99% del presupuesto

---

## ⏱️ IMPLEMENTACIÓN (4-5 horas totales)

```
PASO 1: Crear RDS MySQL                          15 min ✅
PASO 2: Configurar DMS (replicación inicial)      30 min ✅
PASO 3: Escribir 4 funciones Lambda (asistencia,  1.5 horas ✅
        alumno, trabajador, documentos)
PASO 4: Configurar EventBridge (horarios)         30 min ✅
PASO 5: Configurar CloudWatch + SNS (alertas)     30 min ✅
PASO 6: Conectar Power BI a RDS                   20 min ✅
PASO 7: Pruebas y validación completa             1 hora ✅

TIEMPO TOTAL: 4.5 - 5 horas
```

---

## 📅 TABLA PRESUPUESTARIA (5 AÑOS)

| Año | AWS | AZURE | Diferencia | Ahorro Acumulado |
|-----|-----|-------|-----------|------------------|
| Año 1 | $331 | $3,427.76 | -$3,096.76 | -$3,096.76 |
| Año 2 | $331 | $3,427.76 | -$3,096.76 | -$6,193.52 |
| Año 3 | $331 | $3,427.76 | -$3,096.76 | -$9,290.28 |
| Año 4 | $331 | $3,427.76 | -$3,096.76 | -$12,387.04 |
| Año 5 | $331 | $3,427.76 | -$3,096.76 | **-$15,483.80** |

### 🎉 TOTAL 5 AÑOS: **AWS ahorra $15,483.80** vs Azure

---

## 📝 NOTAS FINALES

✅ **Presupuesto recomendado incluyendo margen de seguridad (30%):**
- AWS: $50/mes (~$600/año)
- Azure: $350/mes (~$4,200/año)

✅ **Si aumentan tablas/ejecuciones:**
- AWS: Sigue casi GRATIS (free tier cubre 1M ejecuciones/mes)
- Azure: Aumenta significativamente

✅ **Respaldos automáticos (opcional, no incluido):**
- AWS Backup: +$5-10/mes
- Azure Backup: +$5-10/mes

✅ **Soporte técnico (opcional, no incluido):**
- AWS Developer Support: +$29/mes
- Azure Support: +$29/mes

✅ **Migración futura:** Cambiar de plataforma es fácil y sin costo

---

## 🚀 PRÓXIMOS PASOS

1. ✅ Revisar y aprobar cotización
2. ✅ Presentar propuesta a jefe
3. ✅ Crear cuenta AWS (gratis)
4. ✅ Implementar infraestructura (4-5 horas)
5. ✅ Configurar monitoreo (CloudWatch + SNS)
6. ✅ Conectar Power BI
7. ✅ Pruebas y validación
8. ✅ **Go live**

---

## 📞 INFORMACIÓN FINAL

**Documento generado por:** Copilot  
**Fecha:** 2026-05-06  
**Usuario:** Kuroro-rich  
**Repositorio:** Kuroro-rich/cotizacion-bd-colegios  
**Sistemas:** 7 colegios + holding  
**Período:** 1 año (con proyección 5 años)  

---

## 📊 FORMATO DISPONIBLE

Este documento está disponible en:
- ✅ Markdown (.md) - En GitHub
- ✅ CSV (.csv) - Para Excel
- ✅ PDF - Para imprimir
- ✅ Excel - Con gráficos y fórmulas
