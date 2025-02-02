# helladarion
Notas de RPG no terminal

---

## 1. Visão Geral do Projeto

**Objetivo:**  
Criar um helper para mestres de RPG que opere no terminal (com possibilidade de interface web) para facilitar o gerenciamento de notas e registros durante as sessões. O aplicativo será focado em simplicidade e integração com outros sistemas (como roladores de tesouro e tabelas em Excel).

**Plataformas e Tecnologias:**  
- **Interface Terminal/Web:** Usando [Textual](https://github.com/Textualize/textual) para a interface interativa.  
- **Formato de Notas:** Markdown (.md) para edição e leitura.  
- **Formato de Distribuição:** Arquivos com extensão `.hellaron` (para encapsular as notas e evitar a dispersão em múltiplos arquivos/pastas).  
- **Banco de Dados:** SQLite para armazenar metadados (possivelmente utilizando um modelo EAVT).

---

## 2. Funcionalidades Principais

### 2.1. Registros e Categorias
- **Tipos de Registros:**  
  - **Campanhas:** Armazenamento geral da campanha.  
  - **NPCs:** Informações e perfis dos NPCs.  
  - **Cidades:** Detalhes sobre localidades.  
  - **Sessões:** Registros de sessões de jogo.  
  - **Itens:** Descrições e informações de itens.  
  - **Miscelânea:** Outros registros diversos.
  
- **Organização e Filtragem:**  
  - Sistema de **tags** ou **links** para conectar registros entre si.  
  - Filtros por categorias e tags para facilitar a busca.

### 2.2. Integrações Externas
- **Rolador de Tesouros:**  
  - Integração com um projeto externo para rolar tesouros.  
  - Sistema de API que aceita respostas em um formato padronizado, independente do sistema de RPG.

- **Sincronização com Tabelas (Excel):**  
  - Possibilidade de sincronizar dados, por exemplo, atualizar uma tabela de aliados localmente e disponibilizá-la para os jogadores.

### 2.3. Gerenciamento dos Arquivos de Notas
- **Formato de Notas:**  
  - Notas em Markdown, para que possam ser facilmente lidas tanto pelo aplicativo quanto por outros leitores (como o Glow).

- **Formato `.hellaron`:**  
  - Arquivos compactados ou estruturados de forma única para distribuir as notas sem expor o plain text ou gerar múltiplas pastas.
  - Carregamento na memória ao abrir o aplicativo e regravação ao salvar.

- **Banco de Dados SQLite:**  
  - Armazenar metadados dos registros, como:  
    - Nome  
    - Categoria  
    - Data de criação  
    - Última atualização

---

## 3. Roadmap de Implementação

### 3.1. Fase 1: Lógica e Persistência
- **Desenvolver a Lógica de CRUD:**  
  - Implementar operações de criação, leitura, atualização e exclusão para os registros (campanha, NPCs, cidades, sessões, itens, miscelânea).
  
- **Sistema de Tags e Links:**  
  - Criar a lógica para associar registros por tags ou links e permitir filtragem.

- **Banco de Dados:**  
  - Definir e implementar a estrutura do SQLite para armazenar os metadados.
  - Integrar o carregamento e salvamento dos dados da aplicação com o formato `.hellaron`.

### 3.2. Fase 2: Interface Visual
- **Desenvolver a Interface no Terminal:**  
  - Utilizar o Textual para criar uma interface interativa que possibilite a navegação e edição dos registros.
  
- **Integração com WEB (Opcional):**  
  - Planejar a exposição da aplicação via web, se necessário.

### 3.3. Fase 3: Funcionalidades Adicionais
- **Integração com Rolador de Tesouros:**  
  - Implementar a chamada e o tratamento de respostas da API do rolador.
  
- **Sincronização com Tabelas Excel:**  
  - Desenvolver a funcionalidade para importar/exportar ou sincronizar tabelas.
  
- **Outros Recursos e Melhorias:**  
  - Adicionar quaisquer funcionalidades extras que possam complementar a experiência do usuário, como formatação avançada, templates, etc.

---

## 4. Considerações Finais

- **Modularidade:**  
  - Estruturar o código de forma modular para facilitar futuras integrações e manutenções.

- **Performance e Usabilidade:**  
  - Focar na performance do carregamento/salvamento dos arquivos `.hellaron` e na facilidade de uso da interface, principalmente no ambiente terminal.
