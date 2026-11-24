# NVR Storage Sizing — Dahua DSS7016DR-S2

## Assumptions Declaration

The following calculations use values that were NOT confirmed during the SIWES placement. They are labelled **[ASSUMED]** for clarity.

| Parameter | Value | Confirmation |
|-----------|-------|--------------|
| NVR Model | Dahua DHI-DSS7016DR-S2 | ✅ CONFIRMED (visible on unit) |
| Drive Bays | 16 | ✅ CONFIRMED (physical inspection) |
| Installed Drive Capacity | 16 TB per drive | **[ASSUMED]** — drives labelled Seagate EXOS |
| Drive Count | 16 (all bays filled) | **[ASSUMED]** — visual inspection suggested all populated |
| RAID Configuration | RAID 5 | **[ASSUMED]** — not confirmed via NVR menu |
| Camera Count | 16 | ✅ CONFIRMED |
| Camera Resolution | 1080p | ✅ CONFIRMED |
| Codec | H.265 | **[ASSUMED]** — typical for modern Dahua deployments |
| Bitrate per Camera | 2 Mbps | **[ASSUMED]** — typical H.265 1080p @ 25fps |

## Storage Calculation

### Raw Capacity
16 drives × 16 TB = **256 TB raw**

### Usable Capacity (RAID 5 assumed)
(16 − 1) × 16 TB = **240 TB usable**

### Per-Camera Daily Storage
- 2 Mbps = 2,000,000 bits/sec
- Per day: 2,000,000 × 86,400 = 172.8 Gbit
- Convert: 172.8 / 8 = 21.6 GB
- **~20 GB/day per camera** (using 1024³ conversion)

### All-Camera Daily Storage
16 cameras × 20 GB = **320 GB/day**

### 30-Day Retention
320 GB × 30 = **9.6 TB**

## Conclusion

Even under the assumption of RAID 5, the system provides ~240 TB usable storage against a 30-day requirement of ~9.6 TB — a **25× safety margin**. This allows for:
- Higher resolution cameras (4K)
- Longer retention (up to 1 year)
- Additional cameras (up to 64)

## Recommendations for Verification

To confirm the actual configuration:
1. Check NVR web interface for storage pool status
2. Verify RAID level via NVR menu
3. Read physical drive labels for exact capacity
```
