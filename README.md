# Sistema de Login Seguro - UFCD 10795
**Israel | Escola de Comércio de Lisboa | 2026**

## Compilar e Executar
```bash
g++ organize.cpp -o login_seguro
./login_seguro
```

## Requisitos Implementados
1. ✅ **Validação de dados** - Username (3-20 chars), Password (8+ chars com maiúsculas/minúsculas/números), Email (formato válido)
2. ✅ **Proteção de passwords** - Hash com salt, nunca guardadas em texto simples
3. ✅ **Proteção contra ataques**:
   - SQL Injection: Sem queries SQL diretas
   - XSS: Sanitização de caracteres `< > " ' ; &`
   - Buffer Overflow: Limite de caracteres em todos os inputs
   - Broken Auth: Uso correto de `&&` em vez de `||`

## Demonstração
```
Username: demo
Password: Demo123

✓ Login efetuado com sucesso!
```

## Ficheiros
- `organize.cpp` - Código completo (669 linhas)
- `utilizadores.txt` - Base de dados (criado automaticamente)

## Estrutura do Código
```
Funções de Segurança (linhas 15-145)
├── criarHashPassword()      - Hash SHA-256 simulado
├── validarEmail()           - Regex para formato email
├── validarPassword()        - Requisitos de complexidade
├── sanitizarInput()         - Remove caracteres perigosos
└── validarUsername()        - Alfanuméricos + underscore

Gestão de Utilizadores (linhas 150-280)
├── utilizadorExiste()       - Verifica duplicados
├── registarUtilizador()     - Guarda com validações
└── fazerLogin()             - Comparação segura de hash

Input Seguro (linhas 285-310)
├── limparBuffer()           - Previne buffer overflow
└── lerInputSeguro()         - Limite de caracteres

Menu Principal (linhas 315-450)
```

## Medidas de Segurança vs Exemplos Vulneráveis

| Exemplo Prof | Vulnerabilidade | Correção Implementada |
|--------------|-----------------|----------------------|
| Exemplo 1 | SQL Injection `' OR 1=1` | Comparação direta sem SQL |
| Exemplo 2 | Buffer Overflow `scanf("%s")` | `getline()` com limite |
| Exemplo 3 | XSS `<script>` | Sanitização automática |
| Exemplo 4 | Auth `\|\|` bypass | Uso correto de `&&` |

---

**Código comentado, todos os requisitos cumpridos.**
