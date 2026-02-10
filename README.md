g++ sistema_login_seguro.cpp -o login_seguro
./login_seguro
```

**Teste:**
- Username: `demo_user`
- Password: `Demo2026`
- Email: `demo@escola.pt`

---

## Melhorias vs Versão Base

| Feature | Antes | Depois |
|---------|-------|--------|
| Brute force | Sem proteção | 3 tentativas + 5 min bloqueio |
| Database | Ficheiro simples | Estruturado + timestamps |
| Logging | Básico | Sistema completo |
| Interface | Terminal básico | Profissional |
| Validações | Básicas | Reforçadas |

---

## Segurança Implementada

**Proteções:**
- SQL Injection (sanitização inputs)
- XSS (remove caracteres perigosos)
- Buffer overflow (limites definidos)
- Broken auth (validação correta)
- **Brute force (max 3 tentativas)**

**Passwords:**
- Hash com salt
- Min 8 chars: 1 maiúscula, 1 minúscula, 1 número

**Logging:**
- Timestamps todos eventos
- Tipos: SISTEMA, REGISTO, LOGIN, BLOQUEIO

---

## Demo Brute Force (Principal)
```
Tentativa 1 (errada) → Restam 2
Tentativa 2 (errada) → Resta 1  
Tentativa 3 (errada) → BLOQUEADO 300s

Tentativa com password CORRETA → Recusada (ainda bloqueado)

Após 5 min → Login sucesso
