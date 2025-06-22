# CadQuery Code Generator – Proposed Approach

## Multi-Stage Classification Pipeline

### Overview

This approach introduces a human-inspired pipeline to improve the generation of CadQuery code from part images. The process breaks down visual understanding into interpretable stages that mimic the traditional CAD modeling workflow.

---

### **Stage 1: Mechanical Operation Classification**  
**Goal:** Multi-label classification of manufacturing operations applied to a part (since one part can have multiple operations).

**Target Classes:**  
- **Common Operations:** Drilling, Threading, Filleting, Chamfering, Milling, Facing...  
- **Additional Operations:** Boring, Counterboring, Countersinking, Turning, Grooving, Knurling, Reaming...  

---

### **Stage 2: Face Shape Classification**  
**Goal:** Multi-label classification of geometric shapes or features present on each face or view of the part.  
This stage helps in localizing design intent and surface characteristics.

---

### **Stage 3: Vision-Language Code Generation**  
**Architecture:** Fine-tuned vision-language model that integrates structured inputs.

**Inputs:**  
- Original image of the part  
- Detected operations (from Stage 1)  
- Face-wise shape features (from Stage 2)  

**Output:**  
- Corresponding CadQuery code

**Key Design Feature:**  
Structured intermediate representations act as a semantic bridge between the visual input and the generated code, improving both accuracy and explainability.

---

## Rationale

This staged pipeline mirrors how engineers and designers typically approach CAD modeling:
1. Visual inspection of the part
2. Identification of manufacturing operations and geometric features
3. Sequential construction of the model using appropriate design/code

---

## Expected Benefits

- More accurate code generation through structured feature extraction
- Greater interpretability via step-wise outputs
- Closer alignment with mechanical design reasoning