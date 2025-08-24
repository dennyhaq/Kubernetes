# Learning Roadmap: Kubernetes

Tujuan: Dokumen ini adalah roadmap pembelajaran Kubernetes dalam bahasa Indonesia untuk membantu kontributor dan pembelajar mempelajari dari dasar hingga tingkat lanjut dengan praktik langsung dan proyek.

1. Ringkasan Tingkatan
- Pemula (0-4 minggu): konsep dasar, arsitektur, instalasi lokal, kubectl, Pods, Deployments, Services.
- Menengah (4-12 minggu): konfigurasi, storage, networking, ConfigMaps & Secrets, RBAC, Helm, observability dasar.
- Lanjutan (3-6 bulan): operator & CRD, scheduling & autoscaling, security hardening, CNI & service mesh, GitOps, CI/CD, multi-cluster.
- Spesialisasi & Produksi (6+ bulan): scale besar, troubleshooting, backup & DR, cost optimization, cloud-native patterns.

2. Persiapan Lingkungan
- Alat yang direkomendasikan: kubectl, kind, minikube, k9s, Helm, docker/nerdctl, kubeadm (opsional)
- Instalasi cepat: gunakan kind atau minikube untuk klaster lokal. Contoh: "kind create cluster" atau "minikube start".

3. Roadmap Pembelajaran Terperinci
A. Dasar (minggu 1-4)
- Hari 1-3: Konsep & arsitektur: Node, Pod, Kubelet, API Server, Etcd, Controller Manager, Scheduler.
  Resources: Official docs (kubernetes.io/docs) dan "Kubernetes the Hard Way" (overview).
- Minggu 1: kubectl: create/get/apply/delete logs/exec/describe.
  Latihan: Deploy nginx, scale, lakukan rolling update.
- Minggu 2: Workloads: ReplicaSet, Deployment, StatefulSet, DaemonSet, Job/CronJob.
  Latihan: buat StatefulSet untuk database sederhana.
- Minggu 3: Services & Networking dasar: ClusterIP, NodePort, LoadBalancer, Ingress (NGINX Ingress Controller).
  Latihan: expose aplikasi dengan Ingress.
- Minggu 4: ConfigMaps & Secrets, namespaces, resource limits/quotas.
  Latihan: pindahkan konfigurasi dari image ke ConfigMap dan Secret.

B. Menengah (minggu 5-12)
- Storage: PersistentVolumes, PersistentVolumeClaims, StorageClasses; latihan dengan hostPath (local) dan provisioner cloud.
- Observability: install Prometheus & Grafana, setup basic metrics, buat dashboard sederhana.
- Logging: Fluentd/Fluent Bit + Elasticsearch + Kibana (atau Loki + Promtail + Grafana).
- RBAC & Security: ServiceAccounts, Roles & RoleBindings, NetworkPolicies.
- Package management: Helm: buat dan deploy chart sederhana.
- Latihan proyek: bangun aplikasi 3-tier (frontend, backend, db) lengkap dengan CI (Github Actions) yang build image dan push ke registry; manifest helm untuk deploy.

C. Lanjutan (bulan 3-6)
- Operator & CRD: pahami pattern operator, pelajari contoh operator (Operator SDK) dan buat CRD sederhana.
- Advanced Networking: CNI plugins (Calico, Cilium), service mesh (Istio/Linkerd), mTLS basics.
- Scaling & Reliability: HPA/VPA, cluster-autoscaler, Pod disruption budgets, readiness/liveness probes.
- Security hardening: Pod Security Admission (PSA), image scanning, admission controllers, OPA/Gatekeeper.
- GitOps & CD: ArgoCD atau Flux; pipeline promotion, rollback strategies.
- Multi-cluster & federation: konsep dan tool (e.g., Cluster API, KubeFed overview).

D. Produksi & Spesialisasi (6 bulan ke atas)
- Troubleshooting at scale: kubectl troubleshooting, logs, metrics, eBPF tools (bpftool), performance tuning.
- Backup & Restore: Velero, etcd snapshot strategies.
- Cost & Ops: monitoring cost, autoscaling policies, node pools & taints, provisioning strategies.
- Certification & karir: CKA, CKAD, CKS (persiapan ujian dan simulasi waktu).

4. Roadmap Mingguan & Milestone
Contoh 12-minggu plan compact:
- Week 1-2: Fundamentals & kubectl labs
- Week 3-4: Workloads & Networking
- Week 5-6: Storage & Config
- Week 7-8: Observability & Logging
- Week 9-10: Security & Helm
- Week 11-12: GitOps & Project deploy

5. Sumber Belajar Direkomendasikan
- Official docs: https://kubernetes.io/docs
- Hands-on: Katacoda / Killer.sh / Play with Kubernetes / Kind tutorials
- Books: "Kubernetes Up & Running", "Production Kubernetes"
- Courses: CNCF, Linux Foundation, A Cloud Guru, Udemy (reviewed)
- GitHub projects & examples: kelsey/*, kubernetes/examples

6. Tugas & Projek Direkomendasikan untuk Repository Ini
- /labs/basic: latihan manifest (pod, deployment, service)
- /labs/observability: deploy Prometheus+Grafana, contoh alert
- /labs/helm-chart: contoh chart aplikasi
- /labs/operator: contoh CRD & operator skeleton
- Tambahkan README di setiap folder dengan instruksi setup menggunakan kind

7. Checklist Persiapan Ujian (CKA/CKAD/CKS)
- Kuasai kubectl, manifests, debugging, networking, storage
- Latihan time-boxed labs (timed mock exams)
- Fokus pada troubleshooting dan konfigurasi

8. Cara Berkontribusi pada Roadmap Ini
- Tambahkan issue untuk materi baru
- Submit PR di /labs dengan instruksi dan contoh yang reproducible (gunakan kind)

Penutup: Mulailah dari lingkungan lokal (kind/minikube) dan secara bertahap tambah kompleksitas. Gunakan roadmap ini sebagai pedoman, sesuaikan dengan waktu dan tujuan karir.