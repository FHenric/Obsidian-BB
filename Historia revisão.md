## Checklist de Melhorias Técnicas

- [ ] ****1. Padronização de Exceptions e Mappers****

  -  [ ] Centralizar mapeadores de exceções comuns entre os domínios.

  -  [ ] Garantir mensagens de erro claras e consistentes.

- [ ] ****2. Padronização de Nomes de Domínios****

  -  [ ] Revisar nomes de pacotes e classes para refletir corretamente o contexto de negócio.

  -  [ ] Eliminar inconsistências entre nomes de entidades, serviços e endpoints.

- [ ] ****3. Melhoria na Nomenclatura e Estrutura de DTOs****

  -  [ ] Renomear DTOs para refletir claramente sua função (Request, Response, etc.).

  -  [ ] Eliminar duplicações de DTOs e Exceptions.

  -  [ ] Remover regras de negócio desnecessárias dos DTOs.

  -  [ ] Padronizar nomes conforme o domínio e contexto de uso.

- [ ] ****4. Mapeamento de Erros Previstos e Não Tratados****

  - [ ] Identificar pontos onde erros não estão sendo tratados adequadamente.

  -  [ ] Implementar tratamento consistente para erros esperados (e.g. validações, integrações externas).

- [ ] ****5. Limpeza de Código****

  -  [ ] Remover endpoints depreciados.

  -  [ ] Eliminar métodos sem uso.

  -  [ ] Retirar anotações de restrição que não fazem parte da regra de negócio ou estão sem efeito.

- [ ] ****6. Padronização de Documentação dos Endpoints****

  -  [ ] Uniformizar o uso de anotações Swagger/OpenAPI (`@Operation`, `@Tag`, `@APIResponse`).

  -  [ ] Garantir que todos os endpoints estejam documentados de forma clara e completa.

- [ ] ****7. Padronização de Nomenclatura de Atributos****

  -  [ ] Corrigir inconsistências na nomenclatura de atributos entre camadas (DTO, entidade, serviço).

  -  [ ] Exemplo: padronizar uso de "instância" vs "microsserviço" conforme a regra de negócio.

- [ ] ****8. Versionamento de Endpoints****

  -  [ ] Adotar padrão de versionamento nos endpoints REST (`/v1/...`) para garantir evolução segura da API.

- [ ] ****9. Revisão de Testes Unitários****

  -  [ ] Remover ou ajustar testes comentados.

  -  [ ] Refatorar testes verbosos ou prolixos.

  -  [ ] Revisar cobertura de testes e garantir que os principais fluxos estejam validados.

- [ ] ****10. Aplicação Correta da Autenticação****

  -  [ ] Verificar se todos os endpoints sensíveis estão protegidos com `@Authenticated` e validação da `x-api-key`.