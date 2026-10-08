# Biblioteca Comunitária Saber Livre - Backlog inicial

Responsável: enzosantos-git. Atividade individual de Gestão Ágil de Projetos de Software.

## Contexto e objetivo
Sistema web para substituir fichas e planilhas, permitir consulta pública e controlar a circulação de aproximadamente 4.000 títulos, 9.000 exemplares e 1.500 leitores. Os perfis são visitante, leitor, bibliotecário e coordenador.

Mantidos os sete épicos sugeridos, pois separam resultados de negócio e permitem tratar catálogo, leitores, circulação, reservas, pendências, comunicação e indicadores sem confundir épicos com fases técnicas. As 24 estórias são fatias de comportamento observável, com prioridade e estimativa inicial; os pontos são hipóteses de planejamento a validar com o time.

## Sprint 1
**Duração:** uma semana, de 12 a 18 de outubro de 2026.
**Meta:** permitir ao visitante encontrar um livro disponível e ao bibliotecário cadastrar um leitor, emprestar um exemplar elegível e registrar sua devolução no prazo, mantendo a disponibilidade correta.
**Capacidade assumida:** 17 pontos. Seleção: E1-01 (3), E1-02 (3), E2-01 (3), E3-01 (5), E3-02 (3). Total: 17 pontos. Todas em Pronto para sprint; nenhuma foi implementada.

**Justificativa do MVP:** entrega a jornada completa de consulta, cadastro, retirada e retorno e resolve a incerteza sobre disponibilidade. Presume autenticação básica de bibliotecário incluída nas tarefas de balcão. Como o sistema é novo, a jornada inicial usa empréstimos sem histórico anterior e devoluções no prazo. Reservas, cobrança completa, avisos e relatórios vêm depois. E3-01 deve rejeitar pendências recebidas de E5 e E3-02 deve oferecer os pontos de integração com E4 e E5; antes de liberar devoluções atrasadas e reservas em produção, esses fluxos precisam estar implementados e integrados. Não considerar o MVP uma implementação completa das RN05-RN08.

**Dependências:** E1-01 e E2-01 precedem E3-01; E3-01 precede E3-02; E1-02 acompanha as mudanças de situação. Demais dependências: E3-03 usa E2-02, E4 e E5; E4-02 usa E3-02 e E6-03; E5-01 recebe eventos de E3-02; E5-02 usa E5-01; E6 e E7 dependem dos registros de circulação.

## Decisões e pontos para refinamento
- Datas de empréstimo e multa usam dias corridos e a data local da biblioteca (America/Sao_Paulo); reserva usa 48 horas exatas desde a oferta.
- Renovação acrescenta o prazo do tipo do leitor ao vencimento anterior, interpretação documentada da RN04 a validar com a coordenação.
- CPF único, não duplicar avisos, auditoria de alterações e restrição de reserva de obras de referência são decisões de produto que tornam a operação consistente.
- Leitor ativo no relatório significa ao menos um empréstimo iniciado no período; renovação não conta como novo empréstimo no ranking.
- Refinar: tratamento de leitor bloqueado quando chegar sua vez na fila; reservas duplicadas do mesmo título; renovação no dia do vencimento; pagamento parcial; efeitos da mudança de tipo em empréstimos ativos; autenticação e recuperação de acesso; retenção e descarte de documentos. Não inventar essas regras como se constassem no enunciado.
- LGPD: acesso por perfil, dados pessoais fora do catálogo público e consulta limitada ao próprio leitor. Política de retenção e base legal precisam de definição da biblioteca; este backlog não declara conformidade jurídica completa.

## Fatiamento de estória (comentário para E1-01)
Estória original: “Como bibliotecário, quero gerenciar o acervo, para manter o catálogo atualizado”. Dividida em E1-01 (cadastrar título e exemplar), E1-02 (consultar catálogo público) e E1-03 (atualizar situação operacional). Padrões: divisão por operação e por perfil de usuário. Cada fatia atravessa interface, regra de negócio e persistência e tem resultado verificável. Cadastro e consulta podem entregar valor antes da manutenção; não são divisões por camada técnica.

## Configuração do GitHub Project
- Nome: Biblioteca Saber Livre - Backlog.
- Visibilidade pública; vincular ao repositório biblioteca-backlog-enzosantos-git.
- Labels: épico (#6F42C1), estória (#0E8A16), tarefa (#1D76DB).
- Status: Backlog, Pronto para sprint, Em andamento, Em revisão, Concluído.
- Sprint: Iteration com duração de uma semana; Sprint 1 de 12/10 a 18/10/2026.
- Estimativa: Number. Prioridade: Single select (Alta, Média, Baixa).
- View “Sprint 1”: Board agrupado por Status e filtrado pela iteração Sprint 1.
- View “Backlog por épico”: Table agrupada por Parent issue, exibindo Estimativa, Prioridade e Sprint.
- Cada estória deve ser sub-issue do seu épico; links no texto não substituem Parent issue.
- Copiar a seção Sprint 1 e as decisões deste documento para o README do Project.

## Critério de conclusão das estórias
Critérios de aceite verificados, autorização por perfil respeitada, alterações de estado consistentes e revisão concluída. Pontos e status representam planejamento, não software pronto.


## Links
- [GitHub Project](https://github.com/users/enzosantos-git/projects/2)
- [Estórias e épicos](https://github.com/enzosantos-git/biblioteca-backlog-enzosantos-git/issues)
