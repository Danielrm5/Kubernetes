[⬅️ Anterior: 4. Replica sets](../replica%20sets/) · [🏠 Volver al índice](../README.md)

---

# 🚀 5. Deployments

Un **Deployment** es el recurso de más alto nivel recomendado en producción para desplegar aplicaciones sin estado (*stateless*). Gestiona automáticamente los **ReplicaSets** por debajo para ofrecer control total sobre el ciclo de vida de las versiones.

---

## ✨ ¿Qué aporta un Deployment frente a un ReplicaSet?

| Funcionalidad | Descripción |
| :--- | :--- |
| **🔄 Rolling Updates** | Actualiza la imagen de los Pods de forma gradual sin interrumpir el servicio. |
| **⏪ Rollbacks instantáneos** | Permite volver a una revisión anterior con un solo comando si una actualización falla. |
| **📈 Escalado declarativo** | Ajusta fácilmente el número de réplicas manteniendo el historial de revisiones. |
| **⏸️ Pausa y reanudación** | Permite agrupar varios cambios de configuración antes de lanzar un nuevo despliegue. |

---

## 🛠️ Comandos habituales de `Deployment`

```bash
# Aplicar o actualizar un Deployment
kubectl apply -f deployment.yaml

# Consultar el estado del despliegue y su historial
kubectl rollout status deployment/<nombre>
kubectl rollout history deployment/<nombre>

# Revertir a la versión anterior en caso de fallo
kubectl rollout undo deployment/<nombre>
```

> [!NOTE]
> *En este directorio se irán añadiendo los manifiestos y capturas prácticas correspondientes al módulo de Deployments.*

---

[⬅️ Anterior: 4. Replica sets](../replica%20sets/) · [🏠 Volver al índice](../README.md)
