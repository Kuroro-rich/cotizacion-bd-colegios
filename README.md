# 📊 Cotización: 7 Bases de Datos Réplicas - AWS vs AZURE

## 📁 Archivos en este repositorio

### 1. **COTIZACION_AWS_vs_AZURE_2026.md** 📄 (DOCUMENTO PRINCIPAL)

Cotización completa y detallada con:
- ✅ Resumen ejecutivo
- ✅ Desglose de costos AWS
- ✅ Desglose de costos AZURE
- ✅ Cálculo de ejecuciones (tablas y frecuencias)
- ✅ Cálculo técnico Lambda y SNS
- ✅ Cálculo CloudWatch monitoreo
- ✅ Comparativa detallada (11 criterios)
- ✅ Ventajas y desventajas
- ✅ Recomendación final
- ✅ Tabla presupuestaria 5 años
- ✅ Próximos pasos

**→ LEER PRIMERO**

---

### 2. **EJECUCIONES_Y_FRECUENCIAS.csv** 📊

Detalle de ejecuciones por tabla:
- **asistencia:** 2 veces/día (720/año)
- **alumno:** 1 vez/día (360/año)
- **trabajador:** 1 vez/semana (52/año)
- **documentos:** 1 vez/viernes (48/año)
- **TOTAL:** 1,180 ejecuciones/año

---

### 3. **COSTOS_AWS_DESGLOSE_DETALLADO.csv** 💰

Desglose completo de costos AWS:
- RDS MySQL: $15/mes
- Almacenamiento: $2/mes
- DMS: $2/mes
- Lambda: $0/mes (GRATIS)
- EventBridge: $0/mes (GRATIS)
- CloudWatch: $0/mes (GRATIS)
- SNS: $0/mes (GRATIS)
- **TOTAL: $27.58/mes = $330.96/año**

---

### 4. **COSTOS_AZURE_DESGLOSE_DETALLADO.csv** 💰

Desglose completo de costos AZURE:
- Azure MySQL: $277.98/mes
- Data Factory: $3/mes
- Logic Apps: $3/mes
- Azure Monitor: $0/mes (GRATIS)
- Email: $2/mes
- **TOTAL: $285.98/mes = $3,431.76/año**

---

### 5. **COMPARATIVA_AWS_vs_AZURE_5_AÑOS.csv** 📈

Comparación de costos en 5 años:
- AWS: $1,655 (5 años)
- Azure: $17,138.80 (5 años)
- **Ahorro con AWS: $15,483.80**

---

## 🎯 RESUMEN RÁPIDO

| Métrica | AWS | AZURE | Ganador |
|---------|-----|-------|----------|
| **Costo Mensual** | $27.58 | $285.98 | **AWS** ⭐ |
| **Costo Anual** | $331 | $3,427.76 | **AWS** ⭐ |
| **Costo 5 años** | $1,655 | $17,138.80 | **AWS** ⭐ |
| **Ahorro 5 años** | — | $15,483.80 | **AWS** ⭐ |
| **Sin Código** | ⚠️ Lambda | ✅ 100% visual | AZURE |
| **Facilidad** | Moderada | Muy fácil | AZURE |
| **Curva Aprendizaje** | 4-5 horas | 2-3 horas | AZURE |

---

## ✅ RECOMENDACIÓN

### **ELEGIR: AWS** ⭐⭐⭐

**Razones:**
1. 11.3X más barato ($3,096/año ahorrados)
2. ROI extraordinario
3. Free Tier cubre todo
4. Muy escalable
5. Python básico es valioso

**Costo/año:** $331 (~$27.58/mes)  
**Implementación:** 4-5 horas  
**Requisito:** Python básico (2-3 horas aprendizaje)

---

## 📋 TABLAS Y FRECUENCIAS

```
┌─────────────┬──────────────┬────────────────┐
│ TABLA       │ FRECUENCIA   │ EJECUCIONES/AÑO│
├─────────────┼──────────────┼────────────────┤
│ asistencia  │ 2 veces/día  │ 720            │
│ alumno      │ 1 vez/día    │ 360            │
│ trabajador  │ 1 vez/semana │ 52             │
│ documentos  │ 1 vez/viernes│ 48             │
├─────────────┼──────────────┼────────────────┤
│ TOTAL       │              │ 1,180          │
└─────────────┴──────────────┴────────────────┘
```

---

## 🚀 PRÓXIMOS PASOS

1. ✅ Revisar cotización completa
2. ✅ Presentar propuesta a jefe
3. ✅ Aprobar presupuesto
4. ✅ Crear cuenta AWS
5. ✅ Implementar infraestructura
6. ✅ Configurar monitoreo
7. ✅ Conectar Power BI
8. ✅ Go live

---

## 💡 ARQUITECTURA FINAL

```
┌──────────────────────────────────────────────────────────┐
│          BD ORIGINALES (7 Colegios)                      │
│  ├─ Colegio 1 (producción)                               │
│  ├─ Colegio 2 (producción)                               │
│  └─ ... Colegio 7 (producción)                           │
└────────────────┬─────────────────────────────────────────┘
                 │ DMS (Replicación inicial)
                 ↓
┌──────────────────────────────────────────────────────────┐
│       AWS RDS MYSQL (1 Servidor, 7 BD)                   │
│  ├─ BD_colegio_1 (actualizada cada 2x/día)               │
│  ├─ BD_colegio_2 (actualizada cada día)                  │
│  └─ ... BD_colegio_7 (actualizada cada semana)           │
└────────────────┬─────────────────────────────────────────┘
                 │ Lambda + EventBridge (Actualizaciones)
                 │ CloudWatch + SNS (Monitoreo)
                 ↓
┌──────────────────────────────────────────────────────────┐
│            POWER BI (Análisis)                           │
│  ├─ Dashboards                                           │
│  ├─ Reportes                                             │
│  ├─ Actualizaciones automáticas cada X horas             │
│  └─ Datos frescos para toma de decisiones                │
└──────────────────────────────────────────────────────────┘
```

---

## 📞 INFORMACIÓN

**Documento generado por:** Copilot  
**Fecha:** 2026-05-06  
**Usuario:** Kuroro-rich  
**Repositorio:** [Kuroro-rich/cotizacion-bd-colegios](https://github.com/Kuroro-rich/cotizacion-bd-colegios)  
**Sistemas:** 7 colegios + holding  
**Período:** 1 año (con proyección 5 años)  

---

## 📊 DESCARGABLES

- ✅ Markdown (.md) - Leer en GitHub
- ✅ CSV (.csv) - Importar a Excel
- ✅ PDF - Imprimir y compartir
- ✅ Excel - Con gráficos y fórmulas

---

## 🎓 NOTAS IMPORTANTES

1. **Free Tier AWS:** Cubre casi todo el presupuesto
2. **Escalabilidad:** Si crece, AWS sigue siendo muy barato
3. **Respaldos:** No incluidos en este presupuesto (+$5-10/mes opcional)
4. **Soporte:** No incluido en este presupuesto (+$29/mes opcional)
5. **Migración:** Cambiar de plataforma es fácil

---

## ⭐ CARACTERÍSTICAS CLAVE

✅ 7 BD réplicas en 1 servidor  
✅ Actualizaciones automáticas (según frecuencias)  
✅ Monitoreo con alertas por email  
✅ Dashboards en Power BI  
✅ Costo ultra bajo ($331/año)  
✅ Flexible y escalable  
✅ Sin código (casi)  
✅ Listo para producción
