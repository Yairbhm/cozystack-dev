# Vault (Cozystack external app)

This chart wraps the official [HashiCorp Vault Helm chart](https://github.com/hashicorp/vault-helm) to expose a production-ready configuration for Cozystack tenants. It defaults to HA mode with Raft storage and includes toggles for TLS, persistence, ingress, metrics, and CSI/injector sidecars.

## Key values

- `vault.server.ha.enabled` – Enable HA mode (defaults to `true`).
- `vault.server.ha.replicas` – Number of Vault pods for HA (defaults to `3`).
- `vault.server.ha.raft.enabled` – Use integrated storage with Raft (defaults to `true`).
- `vault.server.ha.raft.setNodeId` – Set deterministic node IDs for Raft peers.
- `vault.server.ha.raft.config` – Raw Vault Raft configuration (includes listener, cluster addr, storage path).
- `vault.server.dataStorage` / `vault.server.auditStorage` – Persistent volumes for data and audit logs.
- `vault.server.service` – Service type and port for Vault API.
- `vault.server.ingress` – Optional ingress with host, class, annotations, and TLS.
- `vault.server.resources` – Requests/limits for Vault pods.
- `vault.injector.enabled` – Enable the Vault Agent Injector webhook (defaults to `true`).
- `vault.csi.enabled` – Enable the Vault CSI provider (defaults to `false`).

Consult the [upstream chart values](https://github.com/hashicorp/vault-helm/blob/main/values.yaml) for the full option set that can be overridden via this wrapper.
