## Documentação Simplificada do Modelo Relacional

*Projeto:* Borbulha

*Data:* 2024-05-09

*Autor:* Isabelle Messias Dantas Pereira

*Objetivo:* A Modelagem de Dados é uma etapa imprescindível para a esquematização de modelos de bancos de dados. Nesse contexto, saber estruturá-los para uma análise adequada das informações é muito importante para garantir a qualidade e a eficiência do sistema.

## Entidades

- *Usuários* (users): Armazena informações básicas sobre os usuários (nome, email, senha e estado).
- *Feed e comunidade* (feed_and_comunity): Armazena os detalhes das postagens feitas no feed ( id do usuário, data de criação, id do tipo de publicação e título, descrição, duração e quantidade de voluntários para o projeto)


## Relacionamentos

- A relação de users e feed_and_comunity é de 1:N 

## Regras de Negócio

- Todos os campos obrigatórios devem ser preenchidos.
- As informações devem ser consistentes entre os formulários.
- Os usuários não podem editar informações já salvas, exceto em casos específicos.
- As informações dos usuários são confidenciais.

## Diagrama



## Considerações Finais

Este modelo relacional simplificado fornece uma base para o gerenciamento eficiente das informações dos usuários e suas respostas nos formulários do projeto Abandono Zero. As entidades, seus atributos e relacionamentos garantem a organização e a integridade dos dados. As regras de negócio garantem a consistência e a confiabilidade das informações.

