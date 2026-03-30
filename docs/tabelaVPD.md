# 📈 Tabela de Referência VPD (Vapor Pressure Deficit)

O VPD mede a capacidade da planta de transpirar e absorver nutrientes. 
- **VPD Baixo:** Planta não transpira (risco de mofo/overfert).
- **VPD Alto:** Planta transpira demais (estresse hídrico/travamento).

## 🎯 Alvos por Fase (em kPa)
- **Seedling/Bercário:** 0.4 - 0.8 kPa (Umidade Alta)
- **Vegetativo:** 0.8 - 1.2 kPa
- **Floração (Engorda):** 1.2 - 1.5 kPa
- **Final de Floração:** 1.5 - 1.6 kPa

## 🌡️ Matriz de Referência Rápida (Temp vs UR)

| Temp | 40% UR | 50% UR | 60% UR | 70% UR |
| :--- | :--- | :--- | :--- | :--- |
| **22°C** | 1.5 kPa | 1.3 kPa | 1.0 kPa | 0.8 kPa |
| **24°C** | 1.8 kPa | 1.5 kPa | 1.2 kPa | 0.9 kPa |
| **26°C** | 2.0 kPa | 1.7 kPa | 1.3 kPa | 1.0 kPa |
| **28°C** | 2.3 kPa | **1.9 kPa** | 1.5 kPa | 1.1 kPa |

---

## 🛠️ Ação Corretiva (Radical Juice - 30/03)
**Status Atual:** ~1.7 kPa (Temp 27.5°C / UR 51%).
- **Objetivo:** Trazer para a faixa de **1.4 - 1.5 kPa**.
- **Como:** Baixar a temperatura para 25°C (Ligar AC) OU subir a UR para 60% (Umidificador).

-------

# 🧮 Lógica de Cálculo de VPD (Simplificada)

Para evitar consultas externas, utilize esta regra de bolso para tomada de decisão rápida no cultivo.

## 📝 A Fórmula "Mental"
O VPD é a diferença entre a umidade que o ar **pode** segurar e a que ele **realmente** segura.
- **Calor aumenta a capacidade do ar:** Quanto mais quente, mais umidade você precisa para manter a planta calma.
- **Frio diminui a capacidade:** No frio, a umidade precisa ser menor para a planta não "sufocar".

💡 Dica de Ouro (Check de Folha)
Sempre considere que a temperatura da folha costuma ser 2ºC menor que a do ar.

## 🛠️ Script de Decisão (Pseudo-código)

```python
if temp >= 28:
    if UR < 55:
        return "ALERTA: VPD MUITO ALTO. Ligar AC ou Umidificador."
    else:
        return "OK: Planta transpirando rápido, mas suportável."

elif temp <= 24:
    if UR > 65:
        return "ALERTA: VPD MUITO BAIXO. Risco de mofo (Botrytis). Ligar exaustão máxima."
    else:
        return "OK: Metabolismo lento, ideal para preservação de terpenos."

else: # Faixa atual (25-26ºC)
    return "SWEET SPOT: Alvo 50-60% UR. Máxima eficiência de engorda."
