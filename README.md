# 🛠 Como Arrumar o XAMPP Quando Dá Pau

> Solução drástica para restaurar o MySQL quando os dados estão corrompidos no XAMPP.

---

## 🧠 Mapa Mental da Solução

```mermaid
mindmap
  root((Solução Drástica))
    Preparar
      - Parar todos os serviços no XAMPP
      - Fechar o Painel
    Pasta MySQL
      - Ir em `C:\xampp\mysql`
    Backup Original
      - Renomear `data` para `data_old`
      - Criar nova pasta `data` vazia
    Estrutura Padrão
      - Copiar de `C:\xampp\mysql\backup` para nova `data`
    Reimportar Bancos
      - Copiar bancos de `data_old` (exceto `mysql`, `phpmyadmin`, `performance_schema`)
      - Colar na nova `data`
    Arquivo Vital
      - Copiar `ibdata1` de `data_old` para nova `data`
    Teste Final
      - Abrir Painel do XAMPP e iniciar MySQL
    Se Falhar
      - Comentar alterações em `my.ini`
      - Verificar `mysql_error.log`
```

---

## ✅ Passo a Passo

Siga este guia cuidadosamente para tentar restaurar seus bancos de dados no MySQL sem perda.

### 1. Parar os Serviços

* No XAMPP, **pare todos os serviços**.
* **Feche o Painel de Controle** completamente.

### 2. Acessar Pasta MySQL

* Navegue até `C:\xampp\mysql`

### 3. Fazer Backup Manual

* Renomeie a pasta `data` para `data_old`
* Crie uma nova pasta **vazia** chamada `data`

### 4. Restaurar Estrutura Original

* Acesse `C:\xampp\mysql\backup`
* Copie **todo o conteúdo** dessa pasta
* Cole dentro da nova pasta `data`

### 5. Reimportar Seus Bancos de Dados

* Acesse `data_old`
* Copie todas as **pastas com nome dos seus bancos de dados** (ex: `meusite`, `wordpress`)
* **Não copie**:

  * `mysql`
  * `phpmyadmin`
  * `performance_schema`
* Cole os bancos copiados na nova pasta `data`

### 6. Substituir o Arquivo `ibdata1`

* Copie o arquivo `ibdata1` de `data_old`
* Cole na nova `data`, substituindo o existente

### 7. Testar Inicialização

* Abra o Painel do XAMPP novamente
* Tente **iniciar o MySQL**

### 8. Se Ainda Não Funcionar...

* Comente as linhas adicionadas recentemente no arquivo `my.ini`
* Verifique o arquivo `mysql_error.log`
* Copie as **10-15 últimas linhas** para diagnóstico mais aprofundado

---

## ⚠️ Aviso Importante

* Essa solução não garante a recuperação total dos dados.
* Sempre faça **backups regulares** dos seus bancos.

---

обезьяна в трусиках
