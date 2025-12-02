# SmartGrade — Inteligência para Desempenho Acadêmico

## Equipe
- André Luiz Flor de Souza Silva — RA: 2225105108  
Turma: 48 | Curso: Ciência da Computação | Período: Noturno | Ano: 2025

## Resumo
SmartGrade é uma solução de aprendizado de máquina que prevê a aprovação de alunos com base em indicadores acadêmicos (horas de estudo, faltas, notas parciais e atividades entregues). O objetivo é permitir intervenções pedagógicas antecipadas para estudantes em risco. Implementamos uma abordagem de classificação supervisionada usando Decision Tree (modelo principal) e Logistic Regression (comparativo). O dataset foi gerado sinteticamente e documentado no repositório. A avaliação é apresentada por acurácia, F1-score e matriz de confusão.

## Problema
Instituições muitas vezes descobrem alunos em risco tarde demais. Uma predição precoce permite ações pedagógicas e acompanhamento individualizado para reduzir reprovações.

## Abordagem de IA
- Tipo: Classificação supervisionada  
- Modelos: Decision Tree (principal) e Logistic Regression (comparativo)  
- Métrica principal: Acurácia. Métrica complementar: F1-score e matriz de confusão.  
- Semente fixada: `random_state=42` (reprodutibilidade)

## Dados
- Origem: Dataset sintético gerado no notebook `SmartGrade.ipynb`.  
- Local: `data/raw/alunos.csv`  
- Colunas:
  - `horas_estudo` (float) — horas de estudo por semana
  - `faltas` (int) — número de faltas
  - `nota1` (float) — nota parcial 1 (0–10)
  - `nota2` (float) — nota parcial 2 (0–10)
  - `atividades_entregues` (int) — 0–10
  - `aprovado` (0/1) — target (1 = aprovado, 0 = reprovado)

## Como reproduzir (Google Colab) — método recomendado
1. Abra https://colab.research.google.com  
2. Crie um novo notebook e renomeie para `SmartGrade.ipynb` OU use a opção *File → Open notebook → GitHub* para abrir este repositório.  
3. Cole/execute as células do notebook (ou abra o notebook salvo aqui).  
4. Execute todas as células (`Runtime → Run all`).  
5. Os modelos serão salvos em `models/` e as figuras em `reports/figures/`.

## Como reproduzir (local)
```bash
python -m venv .venv
# ativar .venv (Windows)
.venv\Scripts\activate
# ativar .venv (Linux/Mac)
source .venv/bin/activate

pip install -r requirements.txt
# executar notebook via jupyter (opcional) ou scripts em src/
jupyter notebook SmartGrade.ipynb
# ou
python src/main.py --seed 42
