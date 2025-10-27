# PhysAug-TS
PhysAug-TS: Physics-Informed Underwater Acoustic Target Recognition via Temporal–Spectral Fusion


> **One-liner.** PhysAug-TS couples **BELLHOP3D physics-consistent multipath CIR augmentation** with a **waveform–Mel temporal–spectral fusion (WMgram)** front-end and a **lightweight multi-scale asymmetric residual CNN (MARNet)**. On DeepShip it achieves **81.58% accuracy** with only **2.31M params / 2.328 GFLOPs**, offering a strong **accuracy–efficiency** trade-off.

---

## 📰 Abstract

Deep learning for underwater acoustic target recognition (UATR) is often constrained by data scarcity, domain shifts, and deployment limits. **PhysAug-TS** addresses these with a pragmatic pipeline:  
1) Generate **coherent multipath CIRs** via **BELLHOP3D** and convolve them with raw waveforms to synthesize **physics-consistent** training samples;  
2) Extract **time-domain features** using a compact 1-D CNN and **align/fuse** them with **log-Mel** features to build **WMgram**;  
3) Feed WMgram to a **lightweight MARNet** backbone (multi-scale asymmetric conv + ECA).  
Using **recording-level splits** on DeepShip, PhysAug-TS yields **81.58% Acc / 81.54% Prec / 81.40% Rec / 81.43% F1** with low compute.

---

## ✨ Highlights

- **Physics-consistent augmentation.** Convolution with coherent multipath CIRs from BELLHOP3D, followed by **center cropping** to avoid boundary artifacts—**explainable** and robust.  
- **Temporal–spectral fusion (WMgram).** Complementary **waveform** and **log-Mel** branches improve separability over single-view features.  
- **Lightweight MARNet.** Multi-scale **asymmetric 1×k / k×1** kernels + residual projections + **ECA** attention deliver **strong accuracy at small model size**.  
- **Reproducible details.** We release splitting guidelines, windowing parameters, augmentation ratios, and kernel/branch sensitivity with **Pareto**-style analysis.

---
