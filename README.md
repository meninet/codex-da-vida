# 🌿 Codex da Vida — Jogo Educativo de Taxonomia e Biodiversidade

**Versão:** 10  
**Componente curricular:** Biologia — 3ª série do Ensino Médio  
**Habilidades BNCC:** EM13CNT202 · EM13CNT202BIO/ES (SEDU-ES)  
**Tema:** Sistemas de Classificação Taxonômica  

---

## Sobre o Jogo

O **Codex da Vida** é um jogo educativo interativo construído em React (arquivo `.jsx` único) que conduz o estudante por uma expedição científica através dos **seis biomas brasileiros**. Guiado pela personagem **Dra. Conceição Ribeiro** — bióloga e naturalista —, o jogador assume o papel de expedicionário e enfrenta desafios progressivos sobre taxonomia, nomenclatura científica, critérios de classificação, ecologia e conservação.

O jogo culmina em uma questão integradora que articula todos os conceitos: *sem nome científico válido, uma espécie não existe para a lei — e não pode ser protegida*.

---

## Versões Disponíveis

O jogo oferece duas versões, selecionáveis na tela inicial:

| Versão | Público-alvo | Características |
|--------|-------------|-----------------|
| **Regular** | Estudantes do Ensino Médio (3ª série) | 6 fases, 33 questões, linguagem científica completa, atividades de arrastar e soltar, dicas com penalidade de pontos |
| **AEE** (Atendimento Educacional Especializado) | Estudantes com necessidades educacionais especiais | 6 fases, 12 questões, linguagem simplificada, texto em caixa alta (via CSS), fonte sans-serif (Lato), atividades por clique (sem drag-and-drop), sem penalidade por dicas |

---

## Estrutura das Fases

### Versão Regular

| Fase | Bioma | Badge | Conteúdo Principal | Pontuação Máx. |
|------|-------|-------|--------------------|----------------|
| 1 | 🌾 Cerrado | Explorador do Cerrado | Hierarquia taxonômica (Domínio → Espécie), cinco reinos, mnemônico DoReFiCOFaGE + atividade de arrastar e soltar | 400 pts |
| 2 | 🌳 Mata Atlântica | Guardião da Mata Atlântica | Critérios de classificação (morfológico, fisiológico, comportamental, molecular), estruturas análogas vs. homólogas, conceito biológico de espécie, cladística | 600 pts |
| 3 | 🌵 Caatinga | Linguista da Caatinga | Nomenclatura binomial de Lineu (5 regras), Princípio da Prioridade, nomes populares vs. científicos | 600 pts |
| 4 | 🌊 Pantanal | Ecólogo do Pantanal | Fatores abióticos e bióticos, Lei do Mínimo (Liebig), Lei da Tolerância (Shelford), nicho ecológico, partilha de recursos + atividade de classificação de fatores | 700 pts |
| 5 | 🐦 Pampa | Guardião do Pampa | Bioma subtropical/temperado, geadas como fator limitante, endemismo, degradação do Pampa, questão integradora com o tuco-tuco-das-dunas | 450 pts |
| 6 | 🌿 Amazônia | Naturalista Amazônico | Síntese de todos os conceitos, megadiversidade brasileira, endemismo, ICZN (holótipo), taxonomia e proteção legal, 3 desafios integradores | 850 pts |

**Pontuação máxima total (regular):** 3.600 pontos

### Versão AEE

Cada fase contém 2 questões com linguagem acessível. A Fase 1 inclui atividade de ordenação por clique (sem arrastar). Pontuação máxima total: 1.300 pontos.

---

## Fluxo do Jogo

```
Tela de Seleção de Versão (Regular / AEE)
    ↓
Tela de Abertura (sinopse do jogo)
    ↓
Tela de Aprendizagens (objetivos + campo de nome)
    ↓
Tela de Missão (briefing + mapa dos biomas IBGE)
    ↓
Fase 1: Cerrado → Fase 2: Mata Atlântica → Fase 3: Caatinga
    → Fase 4: Pantanal → Fase 5: Pampa → Fase 6: Amazônia
    ↓
Tela de Certificado (pontuação final + faixa de desempenho)
```

Cada fase segue a estrutura:
1. **Diálogo de abertura** — Dra. Conceição contextualiza o bioma
2. **Cards de conteúdo** — Material teórico expansível
3. **Atividade interativa** (quando aplicável) — Arrastar e soltar ou classificação
4. **Quiz** — Questões de múltipla escolha com feedback detalhado
5. **Transição** — Badge conquistado + diálogo de encerramento

---

## Mecânicas de Jogo

### Sistema de Pontuação
- Questões regulares: **100 pontos** cada
- Questões integradoras: **150 pontos** cada
- Atividades interativas: **100–150 pontos**
- Uso de dica: **-50% da pontuação** da questão (versão regular)
- Questões integradoras têm **2 dicas** (1ª: -30%, 2ª: -50%)
- Erro após 2 tentativas: **0 pontos** (gabarito exibido)

### Sistema de Dicas
- Cada questão oferece 1 dica (integradoras: 2 dicas)
- Um aviso de penalidade é exibido antes de confirmar o uso
- Na versão AEE, dicas não têm penalidade

### Faixas de Desempenho (Certificado)
| Percentual | Título | Descrição |
|-----------|--------|-----------|
| ≥ 90% | Naturalista Mestre | Domínio excepcional de taxonomia, critérios e ecologia |
| ≥ 75% | Naturalista Pleno | Sólida compreensão dos sistemas de classificação |
| ≥ 60% | Naturalista em Formação | Bom progresso, revisão recomendada |
| < 60% | Aprendiz de Campo | Necessita estudo adicional |

---

## Personagem Guia

**Dra. Conceição Ribeiro** — Bióloga e Naturalista (👩🏾‍🔬)

Presente em todas as fases como mentora, a Dra. Conceição abre cada fase com contextualização narrativa e encerra com reflexão sobre o aprendizado. Sua presença garante coerência narrativa e reforça a conexão entre taxonomia e conservação.

---

## Aspectos Técnicos

### Tecnologia
- **Framework:** React (componente funcional com Hooks)
- **Arquivo único:** `.jsx` autocontido (estilos CSS embutidos via `<style>`)
- **Fontes:** Playfair Display (títulos), Crimson Pro (corpo), Lato (modo AEE)
- **Sem dependências externas** além do React (useState, useRef)
- **Responsivo:** Layout adaptável para desktop e mobile (breakpoint em 600px)

### Acessibilidade (Modo AEE)
- Texto em caixa alta via CSS (`text-transform: uppercase`)
- Fonte sans-serif (Lato) para melhor legibilidade
- Nomes científicos preservados em grafia correta (itálico, sem caixa alta)
- Atividades por clique em vez de drag-and-drop
- Linguagem simplificada e direta
- Badge "AEE" visível no HUD durante o jogo
- Sem penalidade por uso de dicas

### Nomenclatura Científica
Todos os nomes científicos são renderizados em itálico através do componente `<NC>` (Nome Científico), que aplica a classe CSS `.nc { font-style: italic }`. No modo AEE, a classe adicional `.aee-modo .nc` garante que nomes científicos não sejam convertidos para caixa alta (`text-transform: none`).

---

## Conteúdo Pedagógico

### Conceitos Abordados
- Hierarquia taxonômica (Domínio → Espécie)
- Sistema de três domínios (Woese) e cinco reinos (Whittaker)
- Critérios de classificação: morfológico, fisiológico, comportamental e molecular
- Estruturas análogas vs. homólogas
- Conceito biológico de espécie (Mayr, 1942)
- Cladística e grupos monofiléticos
- Nomenclatura binomial de Lineu (5 regras)
- Princípio da Prioridade
- Fatores bióticos e abióticos
- Lei do Mínimo de Liebig (1840)
- Lei da Tolerância de Shelford (1913)
- Nicho ecológico e partilha de recursos
- Endemismo e espécies xéricas
- Níveis de organização ecológica (organismo → bioma)
- Taxonomia como instrumento de conservação e proteção legal
- ICZN (Código Internacional de Nomenclatura Zoológica)
- Déficit taxonômico brasileiro

### Espécies Citadas
O jogo utiliza espécies da fauna e flora brasileira com nomes científicos corretos em itálico, incluindo: *Panthera onca* (onça-pintada), *Chrysocyon brachyurus* (lobo-guará), *Inia geoffrensis* (boto-cor-de-rosa), *Siphonops annulatus* (cobra-cega), *Mimosa tenuiflora* (jurema-preta), *Pteronura brasiliensis* (ariranha), *Ardea alba* (garça-branca-grande), *Caiman yacare* (jacaré-do-pantanal), *Ozotoceros bezoarticus* (veado-campeiro), *Ctenomys flamarioni* (tuco-tuco-das-dunas), *Trichechus inunguis* (peixe-boi-amazônico), entre outras.

---

## Como Usar

O arquivo `codex-da-vida-v10.jsx` é um componente React autocontido. Pode ser executado em qualquer ambiente que suporte React:

1. **Claude.ai** — Faça upload do arquivo `.jsx` diretamente na conversa para renderização imediata como artifact interativo.
2. **Projeto React** — Importe o componente `App` como default export em qualquer aplicação React existente.
3. **CodeSandbox / StackBlitz** — Cole o código em um template React para teste rápido.

---

## Créditos

- **Mapa dos biomas:** IBGE — Instituto Brasileiro de Geografia e Estatística ([educa.ibge.gov.br](https://educa.ibge.gov.br/jovens/conheca-o-brasil/territorio/18307-biomas-brasileiros.html))
- **Alinhamento curricular:** BNCC (EM13CNT202) · SEDU-ES (EM13CNT202BIO/ES)
- **Projeto:** Ciência Plural — Jogo educativo para Biologia, 3ª série do Ensino Médio
