# NotebookLM
## Desafio DIO

O desafio consiste em criar um notebookLM de acordo com o tema que desejar. O meu foi sobre a área de DevOps.
* (https://notebook.google.com/notebook/ba18af01-ebe6-43ee-b11f-ffc906892c0e)


### **Miniguia de Estudo** DEVOPS

---

### 1. Resumos Estruturados do Assunto

#### **A. A Cultura DevOps e a Mentalidade de Aprendizado**
* **Cultura e Colaboração:** DevOps não é apenas um conjunto de ferramentas, mas uma cultura que conecta o desenvolvimento e as operações para entregar software com mais velocidade, estabilidade e segurança. A comunicação clara e a compreensão das necessidades de negócio são tão fundamentais quanto o domínio técnico.
* **Metodologia de Aprendizado:** O aprendizado na área costuma ocorrer via *Problem-Based Learning* (aprendizagem baseada em problemas) e *Just-In-Time Learning* (aprender a teoria necessária exatamente no momento em que um problema real surge em produção).
* **Princípio KISS (*Keep It Simple, Stupid*):** A solução mais simples e direta geralmente é superior a soluções hipercomplexas (*over-engineering*).

#### **B. O Roadmap Técnico em 7 Fases**
1. **Fase 1: Preparação:** Compreensão da arquitetura web (front-end, back-end, APIs), ciclo de vida do software e lógica de programação básica com Python.
2. **Fase 2: Fundamentos Técnicos:** Domínio de comandos Linux no terminal, acessos SSH, controle de versão com Git/GitHub/GitLab e conceitos básicos de redes (IP, DNS, Firewalls, Proxies, Balanceadores de Carga).
3. **Fase 3: Contêineres e Orquestração:** Uso do Docker para empacotar aplicações e dependências (eliminando o problema do "na minha máquina funciona") e Kubernetes para orquestrar contêineres em escala.
4. **Fase 4: Cloud Computing:** Provisionamento de instâncias, armazenamento e redes privadas em provedores de nuvem (com recomendação principal para AWS).
5. **Fase 5: CI/CD e Automação:** Criação de pipelines (GitHub Actions, GitLab CI, Jenkins) para automação de testes, compilação, deploys automáticos, rollbacks e GitOps (ArgoCD).
6. **Fase 6: Monitoramento e Observabilidade:** Acompanhamento da saúde das aplicações e coleta de métricas de performance (Prometheus e Grafana).
7. **Fase 7: Segurança (DevSecOps):** Identificação de vulnerabilidades no código, gestão segura de segredos/senhas e monitoramento de ameaças.

#### **C. Infraestrutura como Código (IaC)**
* **Conceito:** Gerenciamento, provisionamento e configuração de recursos de TI por meio de arquivos de definição legíveis por máquina, armazenados em controle de versão (como o Git).
* **Prevenção do *Configuration Drift*:** Elimina alterações manuais não documentadas que causam inconsistências entre ambientes.
* **Declarativo vs. Imperativo:** O modelo **declarativo** (ex: Terraform) define o estado final desejado e a ferramenta calcula os passos. O modelo **imperativo** especifica a sequência exata de comandos a serem executados.
* **Mutável vs. Imutável:** Na infraestrutura **imutável**, em vez de alterar um servidor existente, ele é descartado e um novo é criado a partir do código atualizado.
* **Ferramentas:** **Terraform** para provisionamento de recursos de nuvem (padrão de mercado) e **Ansible** para gerenciamento de configuração de servidores.

#### **D. Esteira de CI/CD e Tipos de Testes**
* **CI (Integração Contínua):** Automação do processo de build, validação e execução de testes a cada *commit* integrado ao repositório principal.
* **CD (Entrega Contínua vs. Implantação Contínua):** Na *Entrega Contínua* (*Continuous Delivery*), o código é testado e mantido pronto para produção, mas o deploy final exige aprovação manual. Na *Implantação Contínua* (*Continuous Deployment*), a publicação em produção ocorre de forma 100% automatizada sem intervenção humana.
* **Hierarquia de Testes:**
  * *Testes Unitários/Unidade:* Testam pequenas unidades isoladas do código usando Mocks (executados no CI).
  * *Testes de Integração:* Testam a comunicação do código com serviços externos como bancos de dados ou mensageria (executados no CI).
  * *Testes Funcionais (Caixa Preta):* Validam o comportamento do sistema ponta a ponta direto no ambiente implantado (executados no CD).

---

### 2. Glossário com os Principais Conceitos

1. **IaC (Infrastructure as Code):** Prática de definir e provisionar servidores, redes e serviços via arquivos de código versionáveis.
2. **Configuration Drift (Desvio de Configuração):** Inconsistência gerada quando alterações manuais não documentadas são feitas em um ambiente, fazendo com que ele divirja da sua definição original.
3. **Abordagem Declarativa:** Estilo de IaC onde se declara apenas o resultado final esperado do ambiente, deixando a cargo da ferramenta a execução dos passos.
4. **Infraestrutura Imutável:** Paradigma onde componentes de infraestrutura nunca são modificados após criados; qualquer atualização implica na substituição completa do recurso.
5. **CI (Continuous Integration):** Prática de integrar alterações de código frequentemente em um repositório central, executando builds e testes automatizados para detectar erros rapidamente.
6. **Continuous Delivery vs. Continuous Deployment:** A entrega contínua deixa a aplicação automatizada e pronta para release (com gatilho manual), enquanto a implantação contínua publica em produção de forma totalmente automática.
7. **Idempotência:** Propriedade de uma ferramenta ou script de IaC que garante que executá-lo múltiplas vezes resultará exatamente no mesmo estado final, sem criar recursos duplicados ou erros.
8. **Docker & Contêineres:** Tecnologia de virtualização a nível de sistema operacional que empacota a aplicação e todas as suas dependências em uma unidade isolada e padronizada.
9. **Kubernetes (K8s):** Plataforma de orquestração automatizada responsável por escalar, gerenciar e manter a disponibilidade de grupos de contêineres em produção.
10. **Princípio KISS (*Keep It Simple, Stupid*):** Conceito de engenharia que defende a simplicidade no design de soluções, evitando complexidades e problemas inexistentes (*over-engineering*).

---

### 3. Prompts Reutilizáveis para Futuras Revisões

Você pode copiar e colar estes prompts em interações futuras para aprofundar seu aprendizado ou resolver desafios técnicos:

* **Prompt 1: Explicador de Conceitos e Arquitetura de IaC**
  > *"Atue como um Especialista DevOps Sênior. Explique o conceito de [inserir conceito: ex. Módulos do Terraform / Backend Remoto / Idempotência] focando em arquitetura prática. Traga um exemplo prático de código em [HCL / YAML / Python] e mostre quais erros comuns um iniciante deve evitar."*

* **Prompt 2: Guia de Troubleshooting para Pipelines de CI/CD**
  > *"Estou montando uma pipeline de CI/CD no [GitHub Actions / GitLab CI] para uma aplicação conteinerizada. A etapa de [inserir etapa: ex. build da imagem / testes de integração / terraform apply] está falhando com o erro [colar mensagem de erro]. Me ajude a diagnosticar a causa raiz passo a passo e sugira a correção no código YAML."*

* **Prompt 3: Gerador de Exercícios Práticos em Shell Script / Python**
  > *"Crie um exercício prático focado em automação de infraestrutura usando [Bash / Python]. O cenário deve simular um problema real de um DevOps Júnior (ex: verificar espaço em disco e enviar alerta / consumir API da AWS / manipular arquivos de log). Forneça o enunciado, os requisitos e a solução comentada linha por linha."*

* **Prompt 4: Simulação de Entrevista Técnica DevOps**
  > *"Simule uma entrevista técnica para uma vaga de DevOps Júnior/Pleno. Faça 3 perguntas focadas em [Terraform / Docker / CI/CD / Redes]. Espere eu responder cada uma antes de passar para a próxima. Após a minha resposta, dê um feedback construtivo sobre o que posso melhorar do ponto de vista técnico e de comunicação."*

---
