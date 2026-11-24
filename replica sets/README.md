[⬅️ Anterior: 3. PODS](../PODS/) · [🏠 Volver al índice](../README.md) · [➡️ Siguiente: 5. Deployments](../deployments/)

---

# 🔁 4. Replica Sets (Módulo 4)

Un **ReplicaSet** es el controlador de Kubernetes encargado de garantizar que siempre haya un **número específico de réplicas** idénticas de un Pod ejecutándose en todo momento. Si un Pod falla o se elimina, el ReplicaSet crea otro automáticamente para sustituirlo.

---

## 📂 Recursos en [`modulo4`](./modulo4/)

| Archivo | Descripción |
| :--- | :--- |
| [`4.-ReplicaSet.pdf`](./modulo4/4.-ReplicaSet.pdf) | Documentación teórica del Módulo 4 sobre ReplicaSets. |
| [`nginx-rs.yaml`](./modulo4/nginx-rs.yaml) | Manifiesto declarativo de un `ReplicaSet` con 2 réplicas de Nginx. |

---

## 📄 Ejemplo de Manifiesto (`nginx-rs.yaml`)

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: replicaset-nginx
spec:
  replicas: 2
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
        - image: nginx
          name: contenedor-nginx
```

### Elementos clave de un `ReplicaSet`:
- **`replicas`:** cantidad deseada de Pods activos simultáneamente.
- **`selector.matchLabels`:** filtro de etiquetas con el que el ReplicaSet identifica qué Pods están bajo su control.
- **`template`:** plantilla completa con la que se crearán nuevos Pods cuando falten réplicas.

---

## 🛠️ Comandos útiles para trabajar con ReplicaSets

```bash
# Crear el ReplicaSet
kubectl apply -f modulo4/nginx-rs.yaml

# Ver el estado del ReplicaSet y los Pods generados
kubectl get rs,pods -o wide

# Escalar manualmente el número de réplicas
kubectl scale rs/replicaset-nginx --replicas=4
```

---

[⬅️ Anterior: 3. PODS](../PODS/) · [🏠 Volver al índice](../README.md) · [➡️ Siguiente: 5. Deployments](../deployments/)
