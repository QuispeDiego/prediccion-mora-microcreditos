# Diccionario de datos: `creditos_mype.csv`

## Procedencia

Dataset **sintético**, generado con `src/generar_datos.py` (semilla `2026`), autorizado por el docente del curso. Simula la base de créditos MYPE desembolsados por una entidad microfinanciera peruana entre enero 2022 y diciembre 2024, con corte de extracción al **30/06/2025**. Al ser generado por el propio grupo, no está sujeto a licencias de terceros. Las conclusiones obtenidas describen el proceso simulado y no pueden extrapolarse a la población real de microempresarios.

**Unidad de análisis:** un crédito desembolsado (un mismo cliente puede tener varios créditos).
**Variable objetivo:** `mora_30d_6m`.

## Variables

| Variable | Tipo | Descripción |
|---|---|---|
| id_credito | texto | Identificador del crédito |
| id_cliente | texto | Identificador del cliente |
| fecha_solicitud | fecha | Fecha en que se registró la solicitud |
| fecha_desembolso | fecha | Fecha en que se entregó el dinero |
| region | categórica | Región de la agencia que otorgó el crédito |
| codigo_asesor | categórica | Código del asesor de negocios responsable (DIGITAL si no hubo asesor) |
| canal_captacion | categórica | Agencia, Asesor de campo o Digital |
| edad | entero | Edad del titular a la fecha de desembolso |
| sexo | categórica | Sexo del titular |
| estado_civil | categórica | Estado civil del titular |
| nivel_educativo | categórica | Máximo nivel educativo alcanzado |
| tipo_vivienda | categórica | Propia, Familiar o Alquilada |
| num_dependientes | entero | Personas que dependen económicamente del titular |
| rubro | categórica | Actividad principal del negocio |
| antiguedad_negocio_meses | entero | Meses de funcionamiento del negocio |
| ingreso_mensual_declarado | numérico (S/) | Ingreso mensual del negocio declarado en la evaluación |
| gasto_mensual_declarado | numérico (S/) | Gastos mensuales declarados (negocio y familia) |
| cliente_recurrente | categórica | Si el cliente tuvo créditos previos en la entidad |
| num_creditos_previos_entidad | entero | Créditos previos del cliente en la entidad |
| score_buro | numérico | Puntaje de central de riesgo (300 a 950) al momento de la evaluación |
| calificacion_sbs | categórica | Peor calificación en el sistema financiero en los últimos 12 meses |
| max_dias_atraso_12m | entero | Máximo de días de atraso en el sistema en los últimos 12 meses |
| num_entidades_sistema | entero | Entidades financieras con las que mantiene deuda |
| deuda_total_sistema | numérico (S/) | Deuda total en el sistema financiero al momento de la evaluación |
| num_consultas_buro_6m | entero | Consultas a su historial crediticio en los últimos 6 meses |
| monto_solicitado | numérico (S/) | Monto pedido por el cliente |
| monto_aprobado | numérico (S/) | Monto aprobado y desembolsado |
| plazo_meses | entero | Plazo del crédito en meses |
| tasa_interes_anual | numérico (%) | Tasa efectiva anual del crédito |
| cuota_mensual | numérico (S/) | Cuota mensual pactada |
| tiene_garantia | categórica | Si el crédito cuenta con garantía |
| telefono_verificado | categórica | Si el teléfono del titular fue verificado |
| num_gestiones_cobranza | entero | Gestiones registradas por el área de cobranzas hasta la fecha de corte |
| estado_credito_corte | categórica | Estado del crédito a la fecha de corte (30/06/2025) |
| mora_30d_6m | binaria | **Objetivo.** 1 si el crédito superó 30 días de atraso dentro de sus primeros 6 meses |
