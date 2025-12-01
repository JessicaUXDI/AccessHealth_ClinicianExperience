# PeriHealth MD Dashboard

**Clinical Decision Support System with AI-Assisted Differential Diagnosis**

## Overview

PeriHealth is a clinical decision support dashboard designed to help physicians identify patterns across patient visits and correlate signs/symptoms with potential diagnoses based on medical research and clinical guidelines.

### Key Features

- **Personal Baseline vs Population Normal**: Every lab value shows both population reference ranges AND the patient's historical baseline, flagging when values are abnormal *for this specific patient*
- **Cross-Visit Pattern Recognition**: AI analyzes diverse visit types (primary care, specialists, urgent care, PT, dental) to identify clinically significant patterns
- **Transparent Differential Diagnosis**: Ranked diagnoses with confidence levels, supporting/against evidence, and clinical reasoning
- **Collaborative Care Planning**: MD proposes plan items, patient can approve/decline/comment, creating true partnership

## Current State

This is a prototype demonstrating the concept with a sample patient case (perimenopause workup). 

### Roadmap

- [ ] Dynamic symptom input with real-time differential generation
- [ ] Claude API integration for AI-powered clinical reasoning
- [ ] Statistical correlation display (symptom → diagnosis relationships based on medical literature)
- [ ] Multi-condition support (Alzheimer's, diabetes, cardiovascular, etc.)
- [ ] Patient-facing companion app integration

## Getting Started

```bash
# Install dependencies
npm install

# Start development server
npm start

# Build for production
npm run build
```

## Architecture

```
src/
├── index.js          # Entry point
├── App.js            # App wrapper
└── MDDashboardV2.jsx # Main dashboard component (monolithic for now)
```

### Future Architecture

```
src/
├── components/
│   ├── Sidebar/
│   ├── PatientOverview/
│   ├── LabsPanel/
│   ├── DifferentialDx/
│   └── PlanOfCare/
├── services/
│   ├── claudeApi.js      # AI analysis calls
│   └── clinicalData.js   # Medical knowledge base
├── hooks/
│   └── usePatientData.js
└── data/
    └── clinicalCriteria/ # Condition-specific criteria
```

## Clinical Logic

### Personal Baseline System

The system tracks each patient's historical values and calculates deviation:

```javascript
{
  name: 'Estradiol',
  value: 95,           // Current
  refRange: '30-400',  // Population normal
  baseline: 145,       // This patient's normal
  deviation: -34,      // 34% below THEIR baseline
}
```

### AI Pattern Recognition

Cross-visit analysis identifies clusters:
- Musculoskeletal (frozen shoulder + plantar fasciitis + joint pain → estrogen decline)
- Cardiovascular (palpitations + HR elevation → hormone fluctuation)
- Metabolic (LDL rise + weight gain → menopausal transition)

## License

Proprietary - All rights reserved

## Contact

[Your contact info]
