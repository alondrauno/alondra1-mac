# Client requirements

Requirements for Alondra1 for Mac, collected from the [backend specification](https://github.com/alondrauno/alondra1-backend/blob/main/docs/BACKEND_SPEC.md) and its decisions. The specification and the contract in alondra1-backend are the source of truth; update this page when they change.

## Status

Not started.

## Shared rules

Across all clients ([spec §11](https://github.com/alondrauno/alondra1-backend/blob/main/docs/BACKEND_SPEC.md#11-client-requirements)):

- local database schema migrations;
- offline create, edit, complete, and delete;
- user-visible sync status and conflicts;
- no secrets in synced configuration;
- separate local databases or logical partitions per account and space;
- logout revokes the cloud session and offers user-controlled removal of locally cached data.

Rules every client follows:

- **Opt-in cloud** ([ADR 0001](https://github.com/alondrauno/alondra1-backend/blob/main/docs/decisions/0001-opt-in-cloud.md)): the app is fully usable without an account; the cloud is contacted only after the user connects it.
- **Local/cloud boundary** ([ADR 0002](https://github.com/alondrauno/alondra1-backend/blob/main/docs/decisions/0002-local-cloud-task-boundary.md)): what is uploaded and what stays on the device.
- **Sync protocol** ([ADR 0005](https://github.com/alondrauno/alondra1-backend/blob/main/docs/decisions/0005-sync-protocol.md)): outbox with patch composition, conflict queue, expired cursors, lost access. The reference implementation is [`internal/cloudsync/client`](https://github.com/alondrauno/alondra1-backend/tree/main/internal/cloudsync/client).
- **Contract:** the `/v1` API in [openapi.yaml](https://github.com/alondrauno/alondra1-backend/blob/main/contract/openapi.yaml) and the task model in [todo-v1.schema.json](https://github.com/alondrauno/alondra1-backend/blob/main/contract/schemas/todo-v1.schema.json), with the [golden fixture](https://github.com/alondrauno/alondra1-backend/blob/main/contract/fixtures/todo-v1/full-document.json) every client must read and write unchanged.

## Not in scope (until decided)

The mail, calendar, notes, and contacts integrations of the Windows app, and its provider accounts (Microsoft 365, Google, IMAP/POP3/SMTP).
