# Global Agents — OpenCode

---

## linkedin

Generate a personalized LinkedIn message to approach a recruiter based on a job description.

### When to activate

User pastes a job description and asks for a LinkedIn message, recruiter message, or outreach message.

### Instructions

1. Read `cv.md` and `config/profile.yml` from the current working directory. These have the candidate's work history, metrics, and stack. Never invent numbers or achievements.

2. From the job description, identify:
   - Company name and role title
   - 2-3 skills the candidate actually has (matched against cv.md)
   - One past achievement from cv.md that is directly relevant to the role

3. Detect the language: Portuguese JD → write in PT. English JD → write in EN. User request overrides.

4. Generate two versions:

**Connection Request (max 300 characters) — PT:**
```
Olá [NOME], vi a vaga de [CARGO] na [EMPRESA] e fez sentido entrar em contato. [X] anos com [STACK], entregando [ENTREGA CONCRETA]. Adoraria conversar.
```

**Connection Request (max 300 characters) — EN:**
```
Hi [NAME], saw the [ROLE] at [COMPANY] and wanted to reach out. [X] years with [STACK], delivered [CONCRETE RESULT]. Would love to chat.
```

**InMail / Direct message — PT:**
```
Olá [NOME], vi o que a [EMPRESA] está construindo e quis entrar em contato.

Sou Vagner, [X] anos desenvolvendo [CONTEXTO]. Passei pela [EMPRESA DO CV] entregando [ENTREGA CONCRETA]. Stack principal: [2-3 SKILLS].

Não sei se há vagas abertas, mas se houver espaço pra um engenheiro [TIPO] com ownership, adoraria conversar.

Segue meu CV em anexo.
```

**InMail / Direct message — EN:**
```
Hi [NAME], I saw what [COMPANY] is building and wanted to reach out directly.

I'm Vagner, [X] years building [CONTEXT]. Most recently at [COMPANY FROM CV], where I delivered [CONCRETE ACHIEVEMENT]. Main stack: [2-3 SKILLS].

Not sure if there are openings, but if there's room for a [TYPE] engineer with strong ownership, I'd love to chat.

CV attached.
```

5. Humanizer pass — before delivering, verify:
   - No loose skill lists without context
   - No "ampla experiência", "passionate about", "I hope this finds you well"
   - No em dashes in the middle of sentences
   - No "It's not just X, it's Y" constructions
   - One concrete achievement is always better than a list of skills
   - Sentences vary in length — not all the same rhythm
   - Read it out loud mentally. If it sounds robotic, rewrite it.

6. If recruiter name is unknown, use `[NOME]` / `[NAME]` and remind the user to fill it before sending.
