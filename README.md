# Automação de Testes: Selenium + JUnit, Cypress e Playwright

Este repositório apresenta exemplos práticos e modelos de automação de testes utilizando as principais ferramentas do mercado: Selenium + JUnit, Cypress e Playwright. O objetivo é demonstrar minha experiência em automação de testes web, API e integração contínua.

---

## 🚀 Sobre o Repositório

Aqui você encontra:
- Scripts de automação para diferentes cenários e aplicações
- Estrutura de projetos para cada ferramenta
- Exemplos de testes funcionais, de regressão e exploratórios
- Dicas de boas práticas e integração com CI/CD

---

## 🧰 Ferramentas Utilizadas

- **Selenium + JUnit:** Automação de testes web em Java, com exemplos de Page Object, testes de UI e integração com pipelines
- **Cypress:** Testes end-to-end em JavaScript, com cenários de validação de interface, API e mocks
- **Playwright:** Automação multi-browser com exemplos em JavaScript/TypeScript, incluindo testes paralelos e cross-browser

---

## 📂 Estrutura Sugerida

- `/selenium-junit/` — Projetos e scripts em Java
- `/cypress/` — Projetos e exemplos em JavaScript
- `/playwright/` — Projetos e exemplos em JavaScript/TypeScript

---

## 📋 Exemplos de Testes

### Selenium + JUnit
```java
@Test
public void testLoginComSucesso() {
    LoginPage login = new LoginPage(driver);
    login.preencherUsuario("usuario");
    login.preencherSenha("senha");
    login.clicarEntrar();
    Assert.assertTrue(login.dashboardVisivel());
}
```

### Cypress
```javascript
describe('Login', () => {
  it('deve logar com sucesso', () => {
    cy.visit('/login');
    cy.get('#usuario').type('usuario');
    cy.get('#senha').type('senha');
    cy.get('button').contains('Entrar').click();
    cy.contains('Dashboard').should('be.visible');
  });
});
```

### Playwright
```javascript
import { test, expect } from '@playwright/test';

test('login com sucesso', async ({ page }) => {
  await page.goto('https://app.com/login');
  await page.fill('#usuario', 'usuario');
  await page.fill('#senha', 'senha');
  await page.click('text=Entrar');
  await expect(page.locator('text=Dashboard')).toBeVisible();
});
```

---

## 💡 Boas Práticas
- Utilize Page Object para organizar os testes
- Implemente validações claras e assertivas
- Integre os testes com pipelines CI/CD (Jenkins, GitHub Actions)
- Documente cenários e resultados para facilitar a análise

---

> Sinta-se à vontade para contribuir com novos exemplos ou adaptar os modelos conforme a necessidade do seu projeto!
