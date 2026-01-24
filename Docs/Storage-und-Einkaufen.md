
---

### Hardware (Einkaufsliste)

- 1x NVMe SSD (Physisch 1)
- 1x NVMe SSD (Physisch 2)
- 1x SATA HDD
- 2x M.2 Kühlkörper (optional)
- 1x PCIe-Erweiterungskarte (x8 auf 2x M.2)
- SATA-Datenkabel (vorhanden)

---

### Storage-Anbindung

| Komponente | Schnittstelle | Zuordnung |
| --- | --- | --- |
| **SATA SSD** | Onboard SATA | Proxmox Host (Boot) |
| **NVMe 1** | PCIe Adapter (Slot A) | K8s Workload (k3s/Flatcar) |
| **NVMe 2** | PCIe Adapter (Slot B) | Videoschnitt-VM (OS/Proxy) |
| **SATA HDD** | Onboard SATA | Videoschnitt-VM (Archiv via Passthrough) |



Außerdem:

2.5G USB LAN Adapter (2-IN-1)
