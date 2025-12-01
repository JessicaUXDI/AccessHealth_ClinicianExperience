import React, { useState } from 'react';

// Design System - Clinical/Professional
const colors = {
  primary: '#2D5A7B',
  primaryLight: '#4A7A9D',
  primaryDark: '#1E3A5F',
  accent: '#D4896A',
  success: '#5B9A6F',
  warning: '#D4A84A',
  alert: '#C75D5D',
  surface: '#F8FAFC',
  card: '#FFFFFF',
  text: '#1E293B',
  textMuted: '#64748B',
  border: '#E2E8F0',
  divider: '#F1F5F9',
  sidebar: '#1E293B',
  sidebarText: '#94A3B8',
  sidebarActive: '#3B82F6',
};

// Comprehensive patient data with personal baselines
const patientData = {
  id: 'PT-2847561',
  name: 'Jessica Chen',
  age: 47,
  dob: '03/15/1978',
  sex: 'Female',
  pronouns: 'she/her',
  mrn: 'MRN-2847561',
  insurance: 'Blue Cross PPO',
  pcp: 'Dr. Michael Torres',
  
  chiefComplaint: 'Sleep disturbance, cognitive changes, mood instability',
  visitType: 'Hormone Panel Review',
  appointmentDate: 'Dec 3, 2025',
  appointmentTime: '10:30 AM',
  
  vitals: {
    bp: { value: '122/78', status: 'normal', baseline: '118/75', baselineStatus: 'slightly elevated for patient' },
    hr: { value: 72, unit: 'bpm', status: 'normal', baseline: 65, baselineStatus: 'elevated +7 from baseline', flag: true },
    temp: { value: 98.4, unit: '°F', status: 'normal', baseline: 98.2, baselineStatus: 'normal' },
    weight: { value: 156, unit: 'lbs', baseline: 152, change: '+4 lbs (6mo)', baselineStatus: 'gradual increase' },
    respRate: { value: 16, unit: '/min', status: 'normal', baseline: 14, baselineStatus: 'normal' },
    o2Sat: { value: 98, unit: '%', status: 'normal', baseline: 98, baselineStatus: 'normal' },
  },
  
  social: {
    occupation: 'Product Designer (sedentary)',
    maritalStatus: 'Married',
    children: '2 (ages 6, 9)',
    livingSituation: 'House, suburban',
    smokingStatus: 'Never',
    alcoholUse: 'Occasional (2-3 drinks/week)',
    exerciseFrequency: '2x/week (yoga, walking)',
    dietQuality: 'Good (Mediterranean-style)',
    sleepHours: '5-6 hours (disrupted)',
    stressLevel: 'Moderate-High (work deadlines)',
    supportSystem: 'Strong (spouse, friends)',
    healthLiteracy: 'High',
  },
  
  medicalHistory: [
    { condition: 'Anxiety disorder', year: 2018, status: 'Managed' },
    { condition: 'Vitamin D deficiency', year: 2020, status: 'Resolved' },
    { condition: 'Plantar fasciitis', year: 2022, status: 'Resolved' },
    { condition: 'Frozen shoulder (R)', year: 2023, status: 'Resolved' },
  ],
  
  familyHistory: [
    { relation: 'Mother', conditions: ['Breast cancer (age 62)', 'Osteoporosis'] },
    { relation: 'Father', conditions: ['Type 2 diabetes', 'Hypertension'] },
    { relation: 'Sister', conditions: ['Early menopause (age 44)'] },
  ],
  
  medications: [
    { name: 'Escitalopram', dose: '10mg', frequency: 'Daily', indication: 'Anxiety' },
    { name: 'Vitamin D3', dose: '2000 IU', frequency: 'Daily', indication: 'Supplement' },
  ],
  
  allergies: ['Penicillin (rash)', 'Sulfa drugs (hives)'],
  
  // Labs with personal baseline data
  labs: {
    hormones: [
      { 
        name: 'Estradiol', 
        value: 95, 
        unit: 'pg/mL', 
        refRange: '30-400', 
        wnlStatus: 'normal',
        baseline: 145,
        baselineRange: '140-160',
        baselineStatus: 'below',
        deviation: -34,
        deviationNote: '34% below personal baseline',
        trend: 'declining',
        history: [
          { date: 'Mar 2024', value: 145 },
          { date: 'Jun 2024', value: 128 },
          { date: 'Sep 2024', value: 112 },
          { date: 'Nov 2024', value: 95 },
        ],
        insight: 'While within population normal limits, this represents a significant decline from patient\'s established baseline. Pattern consistent with perimenopause transition.'
      },
      { 
        name: 'FSH', 
        value: 28, 
        unit: 'mIU/mL', 
        refRange: '3-10', 
        wnlStatus: 'high',
        baseline: 8,
        baselineRange: '6-10',
        baselineStatus: 'above',
        deviation: 250,
        deviationNote: '250% above personal baseline',
        trend: 'rising',
        history: [
          { date: 'Mar 2024', value: 12 },
          { date: 'Jun 2024', value: 18 },
          { date: 'Sep 2024', value: 23 },
          { date: 'Nov 2024', value: 28 },
        ],
        insight: 'Elevated above both population and personal baseline. Rising FSH with declining estradiol confirms ovarian aging pattern.'
      },
      { 
        name: 'Progesterone', 
        value: 5.2, 
        unit: 'ng/mL', 
        refRange: '5-20', 
        wnlStatus: 'low-normal',
        baseline: 12,
        baselineRange: '10-14',
        baselineStatus: 'below',
        deviation: -57,
        deviationNote: '57% below personal baseline',
        trend: 'declining',
        history: [
          { date: 'Mar 2024', value: 12 },
          { date: 'Jun 2024', value: 9 },
          { date: 'Sep 2024', value: 7 },
          { date: 'Nov 2024', value: 5.2 },
        ],
        insight: 'Low-normal for population but significantly below patient\'s historical levels. May contribute to sleep disruption and mood symptoms.'
      },
      { 
        name: 'LH', 
        value: 22, 
        unit: 'mIU/mL', 
        refRange: '2-15', 
        wnlStatus: 'high',
        baseline: 7,
        baselineRange: '5-9',
        baselineStatus: 'above',
        deviation: 214,
        deviationNote: '214% above personal baseline',
        trend: 'rising',
        history: [
          { date: 'Mar 2024', value: 8 },
          { date: 'Jun 2024', value: 14 },
          { date: 'Sep 2024', value: 18 },
          { date: 'Nov 2024', value: 22 },
        ],
        insight: 'Elevated LH:FSH ratio consistent with perimenopause.'
      },
      { 
        name: 'AMH', 
        value: 0.8, 
        unit: 'ng/mL', 
        refRange: '1-3.5', 
        wnlStatus: 'low',
        baseline: 2.1,
        baselineRange: '2.0-2.5',
        baselineStatus: 'below',
        deviation: -62,
        deviationNote: '62% below personal baseline (age 42)',
        trend: 'declining',
        history: [
          { date: 'Mar 2021', value: 2.1 },
          { date: 'Mar 2023', value: 1.4 },
          { date: 'Nov 2024', value: 0.8 },
        ],
        insight: 'Indicates diminished ovarian reserve. Rate of decline is within expected range for age.'
      },
    ],
    thyroid: [
      { name: 'TSH', value: null, unit: 'mIU/L', refRange: '0.4-4.0', wnlStatus: 'pending', baseline: 1.8, baselineRange: '1.5-2.0' },
      { name: 'Free T4', value: null, unit: 'ng/dL', refRange: '0.8-1.8', wnlStatus: 'pending', baseline: 1.2, baselineRange: '1.1-1.3' },
    ],
    metabolic: [
      { name: 'Glucose (fasting)', value: 94, unit: 'mg/dL', refRange: '70-99', wnlStatus: 'normal', baseline: 88, baselineStatus: 'slightly elevated', insight: 'Trending up from baseline 88. Monitor given family history of diabetes.' },
      { name: 'HbA1c', value: 5.4, unit: '%', refRange: '<5.7', wnlStatus: 'normal', baseline: 5.2, baselineStatus: 'normal' },
      { name: 'Total Cholesterol', value: 198, unit: 'mg/dL', refRange: '<200', wnlStatus: 'normal', baseline: 178, baselineStatus: 'elevated', insight: 'Increased 20 points over 2 years. Estrogen decline may be contributing to lipid changes.' },
      { name: 'LDL', value: 118, unit: 'mg/dL', refRange: '<100', wnlStatus: 'borderline', baseline: 95, baselineStatus: 'elevated', insight: 'Was consistently <100 until this year. Correlates with hormone changes.' },
      { name: 'HDL', value: 62, unit: 'mg/dL', refRange: '>50', wnlStatus: 'normal', baseline: 68, baselineStatus: 'decreased', insight: 'Slight decrease from baseline. HDL often declines with estrogen.' },
      { name: 'Triglycerides', value: 92, unit: 'mg/dL', refRange: '<150', wnlStatus: 'normal', baseline: 85, baselineStatus: 'normal' },
    ],
    other: [
      { name: 'Vitamin D', value: 38, unit: 'ng/mL', refRange: '30-100', wnlStatus: 'normal', baseline: 28, baselineStatus: 'improved', insight: 'Improved with supplementation. Continue current dose.' },
      { name: 'B12', value: 485, unit: 'pg/mL', refRange: '200-900', wnlStatus: 'normal', baseline: 520, baselineStatus: 'normal' },
      { name: 'Ferritin', value: 42, unit: 'ng/mL', refRange: '12-150', wnlStatus: 'normal', baseline: 55, baselineStatus: 'slightly low', insight: 'Trending down. May reflect heavier periods during perimenopause.' },
    ],
  },
  
  // Diverse visit history
  visitHistory: [
    {
      date: 'Nov 15, 2024',
      type: 'Lab Work',
      provider: 'Quest Diagnostics',
      department: 'Laboratory',
      reason: 'Hormone panel, metabolic panel',
      findings: ['Elevated FSH (28)', 'Declining estradiol (95)', 'LDL borderline (118)'],
      aiTags: ['hormone-change', 'lipid-change'],
    },
    {
      date: 'Oct 22, 2024',
      type: 'Telehealth',
      provider: 'Dr. Sarah Chen',
      department: 'OB-GYN',
      reason: 'Sleep concerns, mood changes',
      findings: ['Reports 3am waking x 3 months', 'Increased irritability', 'Brain fog affecting work', 'Cycle still regular but lighter'],
      plan: ['Order hormone panel', 'Discussed perimenopause possibility', 'Sleep hygiene counseling'],
      aiTags: ['sleep-disruption', 'mood-change', 'cognitive'],
    },
    {
      date: 'Aug 8, 2024',
      type: 'Urgent Care',
      provider: 'Dr. Kevin Park',
      department: 'Urgent Care',
      reason: 'Heart palpitations, anxiety',
      findings: ['HR 92 (elevated for patient)', 'ECG normal sinus rhythm', 'Palpitations described as "fluttering"', 'Occurred during period week'],
      plan: ['Reassurance - likely benign', 'Follow up with PCP if persists'],
      aiTags: ['cardiovascular', 'anxiety', 'hormone-related'],
    },
    {
      date: 'Jun 12, 2024',
      type: 'Annual Exam',
      provider: 'Dr. Michael Torres',
      department: 'Primary Care',
      reason: 'Annual wellness visit',
      findings: ['BP 118/76', 'Weight 154 lbs', 'Reports increased fatigue', 'Anxiety well-controlled on current medication', 'Due for mammogram'],
      plan: ['Continue escitalopram', 'Mammogram ordered', 'Recheck lipids in 6 months'],
      aiTags: ['wellness', 'fatigue'],
    },
    {
      date: 'Mar 5, 2024',
      type: 'Lab Work',
      provider: 'Quest Diagnostics',
      department: 'Laboratory',
      reason: 'Routine labs',
      findings: ['All values WNL', 'Estradiol 128', 'FSH 18 (slightly elevated)', 'Lipids normal'],
      aiTags: ['hormone-change'],
    },
    {
      date: 'Jan 18, 2024',
      type: 'Physical Therapy',
      provider: 'Bay Area PT',
      department: 'Physical Therapy',
      reason: 'Right shoulder stiffness (frozen shoulder)',
      findings: ['Limited ROM right shoulder', 'Adhesive capsulitis diagnosed', 'No trauma history'],
      plan: ['PT 2x/week x 8 weeks', 'Home exercises', 'Consider cortisone if no improvement'],
      outcome: 'Resolved after 10 weeks PT',
      aiTags: ['musculoskeletal', 'unexplained'],
    },
    {
      date: 'Sep 14, 2023',
      type: 'Specialist',
      provider: 'Dr. Lisa Wong',
      department: 'Rheumatology',
      reason: 'Joint pain, stiffness evaluation',
      findings: ['Mild joint stiffness AM', 'No swelling or redness', 'RF negative', 'ANA negative', 'Uric acid normal'],
      plan: ['NSAIDs PRN', 'Follow up if worsens', 'Likely not inflammatory arthritis'],
      aiTags: ['musculoskeletal', 'ruled-out-autoimmune'],
    },
    {
      date: 'May 22, 2023',
      type: 'Dental',
      provider: 'Dr. James Lee',
      department: 'Dentistry',
      reason: 'Routine cleaning + cavities',
      findings: ['2 new cavities (first in 10 years)', 'Gum recession noted', 'Reports dry mouth'],
      plan: ['Fillings completed', 'Prescription fluoride toothpaste', 'Increase water intake'],
      aiTags: ['oral-health', 'unexplained'],
    },
    {
      date: 'Nov 3, 2022',
      type: 'Podiatry',
      provider: 'Dr. Robert Kim',
      department: 'Podiatry',
      reason: 'Heel pain',
      findings: ['Plantar fasciitis bilateral', 'No prior foot problems', 'No change in activity'],
      plan: ['Stretching protocol', 'Night splints', 'Supportive shoes'],
      outcome: 'Resolved after 4 months',
      aiTags: ['musculoskeletal', 'unexplained'],
    },
    {
      date: 'Mar 15, 2021',
      type: 'Lab Work',
      provider: 'Quest Diagnostics',
      department: 'Laboratory',
      reason: 'Baseline hormone panel (age 43)',
      findings: ['Estradiol 145 (established baseline)', 'FSH 8 (normal)', 'AMH 2.1 (normal for age)'],
      aiTags: ['baseline'],
    },
  ],
  
  // AI-detected patterns across visits
  aiPatterns: [
    {
      id: 1,
      title: 'Musculoskeletal Cluster',
      confidence: 89,
      severity: 'moderate',
      description: 'Pattern of unexplained musculoskeletal issues appearing without trauma or inflammatory markers.',
      connectedVisits: ['Jan 2024 - Frozen shoulder', 'Sep 2023 - Joint stiffness', 'Nov 2022 - Plantar fasciitis'],
      labCorrelation: 'Correlates with declining estrogen (145→95 pg/mL over same period)',
      insight: 'Estrogen receptors exist in joints, tendons, and fascia. Declining estrogen can cause musculoskeletal symptoms that mimic other conditions. This cluster is highly consistent with perimenopause.',
      clinicalImplication: 'Consider HRT as potential treatment for musculoskeletal symptoms, not just vasomotor.',
    },
    {
      id: 2,
      title: 'Cardiovascular Symptoms + Hormone Changes',
      confidence: 82,
      severity: 'mild',
      description: 'Palpitations and elevated resting HR correlating with hormone fluctuations.',
      connectedVisits: ['Aug 2024 - Urgent care for palpitations', 'Current - HR 72 vs baseline 65'],
      labCorrelation: 'FSH spike (18→28) occurred in same timeframe as palpitation episode',
      insight: 'Estrogen affects cardiac conduction and vascular tone. Palpitations are common in perimenopause but often attributed to anxiety.',
      clinicalImplication: 'Palpitations likely hormone-related given normal ECG. May improve with HRT. Continue monitoring.',
    },
    {
      id: 3,
      title: 'Oral Health Deterioration',
      confidence: 76,
      severity: 'mild',
      description: 'New cavities and gum recession in patient with previously excellent dental health.',
      connectedVisits: ['May 2023 - 2 new cavities, gum recession, dry mouth'],
      labCorrelation: 'Occurred as estrogen began declining (estradiol was ~130 at time)',
      insight: 'Estrogen maintains oral mucosa and saliva production. Dry mouth increases cavity risk. Gum recession accelerates with hormone decline.',
      clinicalImplication: 'Counsel patient on increased dental vigilance during perimenopause. Consider saliva substitutes.',
    },
    {
      id: 4,
      title: 'Metabolic Shift',
      confidence: 85,
      severity: 'moderate',
      description: 'Lipid profile worsening despite stable diet and exercise.',
      connectedVisits: ['Nov 2024 labs - LDL 118 (was 95)', 'Jun 2024 - Weight 154→156'],
      labCorrelation: 'LDL increase coincides with estradiol decline below 100',
      insight: 'Estrogen is cardioprotective and helps maintain favorable lipid profiles. Perimenopausal women often see LDL rise and HDL fall.',
      clinicalImplication: 'Cardiovascular risk increases post-menopause. Early HRT may help preserve lipid profile. Consider statin if continues.',
    },
  ],
  
  trackedSymptoms: [
    { symptom: '3am waking', frequency: 5, days: 7, severity: 'moderate', trend: 'worsening' },
    { symptom: 'Brain fog', frequency: 4, days: 7, severity: 'moderate', trend: 'stable' },
    { symptom: 'Rage/Irritability', frequency: 3, days: 7, severity: 'severe', trend: 'worsening' },
    { symptom: 'Anxiety', frequency: 3, days: 7, severity: 'moderate', trend: 'stable' },
    { symptom: 'Mood swings', frequency: 2, days: 7, severity: 'moderate', trend: 'new' },
    { symptom: 'Heart palpitations', frequency: 2, days: 7, severity: 'mild', trend: 'stable' },
    { symptom: 'Joint pain', frequency: 1, days: 7, severity: 'mild', trend: 'new' },
  ],
  
  concerns: [
    { text: 'Waking up at 3am most nights and can\'t fall back asleep for hours. Affecting my work performance.', priority: 'high' },
    { text: 'Brain fog is getting worse - forgetting words mid-sentence, losing train of thought in meetings.', priority: 'high' },
    { text: 'Mood swings are affecting my family. I feel irritable then tearful within minutes.', priority: 'medium' },
    { text: 'Worried about my mom\'s breast cancer history - is HRT safe for me?', priority: 'high' },
  ],
  
  questions: [
    'Is this perimenopause even though I still have regular periods?',
    'What are my treatment options beyond just waiting it out?',
    'Are there risks to hormone therapy given my family history?',
    'Could this be thyroid related instead?',
  ],
};

// Differential diagnosis with full clinical detail
const differentialDiagnosis = [
  {
    diagnosis: 'Perimenopause / Menopause Transition',
    icd10: 'N95.1',
    likelihoodRatio: 12.4,
    confidenceInterval: '8.2 - 18.7',
    aiConfidence: 94,
    reasoning: 'Age 47, FSH elevated (28), declining estradiol trend, classic symptom cluster, multi-system involvement pattern (MSK, cardiac, oral, cognitive, mood), family history of early menopause in sister (age 44).',
    
    // Symptom incidence - how often each symptom appears in this diagnosis
    symptomIncidence: [
      { symptom: 'Sleep disruption / 3am waking', patientHas: true, incidence: 84, note: 'One of the earliest and most persistent symptoms' },
      { symptom: 'Vasomotor symptoms (hot flashes, night sweats)', patientHas: true, incidence: 80, note: 'Hallmark symptom, though not required for diagnosis' },
      { symptom: 'Mood changes / irritability', patientHas: true, incidence: 70, note: 'Often precedes vasomotor symptoms' },
      { symptom: 'Cognitive changes (brain fog)', patientHas: true, incidence: 62, note: 'Correlates with estradiol fluctuation' },
      { symptom: 'Irregular menstrual cycles', patientHas: false, incidence: 90, note: 'Patient still regular — early perimenopause' },
      { symptom: 'Joint/muscle pain', patientHas: true, incidence: 54, note: 'Under-recognized; estrogen receptors in MSK tissue' },
      { symptom: 'Palpitations', patientHas: true, incidence: 42, note: 'Often misattributed to anxiety' },
      { symptom: 'Weight gain', patientHas: true, incidence: 60, note: 'Metabolic shift with declining estrogen' },
      { symptom: 'Decreased libido', patientHas: false, incidence: 52, note: 'Not reported by patient' },
    ],
    
    supportingEvidence: [
      { type: 'lab', text: 'FSH 28 mIU/mL — 250% above personal baseline' },
      { type: 'lab', text: 'Estradiol 95 pg/mL — 34% below personal baseline' },
      { type: 'lab', text: 'AMH 0.8 ng/mL — diminished ovarian reserve' },
      { type: 'pattern', text: 'AI: Musculoskeletal cluster (89% confidence)' },
      { type: 'pattern', text: 'AI: Cardiovascular correlation (82% confidence)' },
      { type: 'history', text: 'Sister with early menopause (age 44)' },
      { type: 'age', text: 'Age 47 — within typical perimenopause window (45-55)' },
    ],
    againstEvidence: [
      { type: 'history', text: 'Still having regular periods' },
    ],
    
    // Assessment criteria for ruling in/out
    assessmentCriteria: {
      ruleIn: [
        { criterion: 'STRAW+10 Stage -2 or beyond', status: 'likely', description: 'Variable cycle length, elevated FSH, declining AMH' },
        { criterion: 'FSH > 25 mIU/mL on day 2-4', status: 'met', description: 'FSH 28 mIU/mL (patient baseline was 8)' },
        { criterion: 'Estradiol declining trend', status: 'met', description: '145 → 128 → 112 → 95 pg/mL over 8 months' },
        { criterion: 'Symptom cluster consistent with estrogen withdrawal', status: 'met', description: 'Sleep, mood, cognitive, vasomotor symptoms present' },
      ],
      ruleOut: [
        { criterion: 'Thyroid dysfunction excluded', status: 'pending', description: 'TSH/Free T4 results pending — required before confirming' },
        { criterion: 'Primary psychiatric disorder excluded', status: 'likely', description: 'Symptoms correlate with hormone changes, stable on current SSRI' },
        { criterion: 'Other endocrine disorders excluded', status: 'met', description: 'No signs of adrenal, pituitary, or other dysfunction' },
      ],
    },
    
    recommendedWorkup: [
      { test: 'TSH + Free T4', priority: 'high', rationale: 'Rule out thyroid dysfunction (results pending)' },
      { test: 'Repeat FSH/Estradiol', priority: 'medium', rationale: 'Confirm pattern if diagnosis uncertain' },
      { test: 'Mammogram', priority: 'high', rationale: 'Required before HRT initiation; family history of breast cancer' },
      { test: 'DEXA scan', priority: 'medium', rationale: 'Baseline bone density given family history of osteoporosis' },
    ],
    
    clinicalDecisionSteps: [
      { step: 1, action: 'Confirm thyroid results are normal', status: 'pending' },
      { step: 2, action: 'Complete menstrual history assessment', status: 'pending', questions: ['LMP?', 'Cycle length changes past 12 months?', 'Flow changes?'] },
      { step: 3, action: 'Assess vasomotor symptom severity (Greene Climacteric Scale or similar)', status: 'pending' },
      { step: 4, action: 'Review contraindications to HRT', status: 'pending', considerations: ['Family breast cancer history', 'Thrombosis risk', 'Cardiovascular risk'] },
      { step: 5, action: 'Discuss treatment options with patient', status: 'pending' },
    ],
  },
  {
    diagnosis: 'Hypothyroidism',
    icd10: 'E03.9',
    likelihoodRatio: 2.1,
    confidenceInterval: '1.2 - 3.8',
    aiConfidence: 91,
    reasoning: 'Significant symptom overlap with perimenopause. Must rule out before attributing symptoms to menopause transition.',
    
    symptomIncidence: [
      { symptom: 'Fatigue', patientHas: true, incidence: 92, note: 'Cardinal symptom' },
      { symptom: 'Weight gain', patientHas: true, incidence: 78, note: 'Due to decreased metabolic rate' },
      { symptom: 'Cognitive changes (brain fog)', patientHas: true, incidence: 72, note: 'Common complaint' },
      { symptom: 'Cold intolerance', patientHas: false, incidence: 68, note: 'Not reported — argues against' },
      { symptom: 'Constipation', patientHas: false, incidence: 64, note: 'Not reported' },
      { symptom: 'Dry skin', patientHas: false, incidence: 76, note: 'Not reported' },
      { symptom: 'Depression/mood changes', patientHas: true, incidence: 60, note: 'Present but pattern atypical' },
      { symptom: 'Menstrual irregularity', patientHas: false, incidence: 58, note: 'Patient has regular cycles' },
      { symptom: 'Hair loss', patientHas: false, incidence: 52, note: 'Not reported' },
    ],
    
    supportingEvidence: [
      { type: 'symptom', text: 'Fatigue, cognitive changes, mood instability' },
      { type: 'symptom', text: 'Weight gain (+4 lbs over 6 months)' },
    ],
    againstEvidence: [
      { type: 'history', text: 'No personal or family thyroid history' },
      { type: 'history', text: 'Historical TSH always normal (baseline 1.8 mIU/L)' },
      { type: 'symptom', text: 'No cold intolerance, constipation, or dry skin' },
      { type: 'pattern', text: 'Symptom onset/pattern better fits hormone fluctuation than steady thyroid decline' },
    ],
    
    assessmentCriteria: {
      ruleIn: [
        { criterion: 'TSH > 4.5 mIU/L', status: 'pending', description: 'Results expected before visit' },
        { criterion: 'Free T4 < 0.8 ng/dL', status: 'pending', description: 'Would confirm if TSH elevated' },
        { criterion: 'Positive TPO antibodies', status: 'not ordered', description: 'Would suggest Hashimoto\'s if TSH abnormal' },
      ],
      ruleOut: [
        { criterion: 'TSH within normal limits', status: 'pending', description: 'If TSH normal, diagnosis effectively ruled out' },
        { criterion: 'Absence of classic hypothyroid signs', status: 'met', description: 'No goiter, no delayed reflexes, no periorbital edema' },
      ],
    },
    
    recommendedWorkup: [
      { test: 'TSH', priority: 'high', rationale: 'Primary screening test (pending)' },
      { test: 'Free T4', priority: 'high', rationale: 'Confirms diagnosis if TSH abnormal (pending)' },
      { test: 'TPO antibodies', priority: 'low', rationale: 'Only if TSH elevated — identifies autoimmune etiology' },
    ],
    
    clinicalDecisionSteps: [
      { step: 1, action: 'Review TSH results when available', status: 'pending' },
      { step: 2, action: 'If TSH > 4.5: Check Free T4, consider TPO antibodies', status: 'conditional' },
      { step: 3, action: 'If TSH normal: Rule out hypothyroidism, focus on perimenopause', status: 'conditional' },
      { step: 4, action: 'Compare to patient baseline TSH (1.8)', status: 'pending', note: 'Even "normal" TSH that\'s elevated from baseline may be significant' },
    ],
    
    ruleOut: true,
  },
  {
    diagnosis: 'Major Depressive Disorder',
    icd10: 'F32.9',
    likelihoodRatio: 1.4,
    confidenceInterval: '0.8 - 2.4',
    aiConfidence: 88,
    reasoning: 'Mood symptoms present, but temporal pattern and symptom cluster suggest hormone-related mood changes rather than primary depressive disorder.',
    
    symptomIncidence: [
      { symptom: 'Depressed mood', patientHas: false, incidence: 96, note: 'Not prominently reported — irritability instead' },
      { symptom: 'Anhedonia', patientHas: false, incidence: 84, note: 'Not reported — argues strongly against' },
      { symptom: 'Sleep disturbance', patientHas: true, incidence: 88, note: 'Present but pattern (3am waking) more typical of perimenopause' },
      { symptom: 'Fatigue', patientHas: true, incidence: 92, note: 'Present' },
      { symptom: 'Concentration difficulty', patientHas: true, incidence: 78, note: 'Present' },
      { symptom: 'Appetite/weight change', patientHas: true, incidence: 72, note: 'Weight gain present but gradual' },
      { symptom: 'Psychomotor changes', patientHas: false, incidence: 58, note: 'Not observed' },
      { symptom: 'Guilt/worthlessness', patientHas: false, incidence: 68, note: 'Not reported' },
      { symptom: 'Suicidal ideation', patientHas: false, incidence: 52, note: 'Denied' },
    ],
    
    supportingEvidence: [
      { type: 'symptom', text: 'Mood changes, irritability present' },
      { type: 'history', text: 'History of anxiety disorder (2018)' },
      { type: 'symptom', text: 'Sleep disruption and fatigue' },
    ],
    againstEvidence: [
      { type: 'pattern', text: 'Symptom onset correlates with hormone changes, not life stressors' },
      { type: 'medication', text: 'Stable on SSRI (Escitalopram 10mg) with good prior control' },
      { type: 'symptom', text: 'No anhedonia — still enjoying activities' },
      { type: 'symptom', text: 'No suicidal ideation, guilt, or worthlessness' },
      { type: 'symptom', text: 'Irritability > sadness — more typical of hormone fluctuation' },
    ],
    
    assessmentCriteria: {
      ruleIn: [
        { criterion: 'DSM-5: 5+ symptoms for 2+ weeks', status: 'not met', description: 'Only 3 of 9 criteria clearly present' },
        { criterion: 'PHQ-9 score ≥ 10', status: 'not assessed', description: 'Formal screening recommended' },
        { criterion: 'Symptoms cause significant impairment', status: 'partial', description: 'Work impact reported but functioning maintained' },
      ],
      ruleOut: [
        { criterion: 'Symptoms better explained by medical condition', status: 'likely', description: 'Perimenopause more likely given hormone changes and symptom pattern' },
        { criterion: 'No anhedonia or persistent depressed mood', status: 'met', description: 'Core features of MDD absent' },
        { criterion: 'Current treatment effective for baseline anxiety', status: 'met', description: 'SSRI controlling prior anxiety symptoms' },
      ],
    },
    
    recommendedWorkup: [
      { test: 'PHQ-9', priority: 'high', rationale: 'Formal depression screening to quantify severity' },
      { test: 'GAD-7', priority: 'high', rationale: 'Assess anxiety component given history' },
      { test: 'Review SSRI adequacy', priority: 'medium', rationale: 'Consider dose optimization if mood symptoms persist after HRT trial' },
    ],
    
    clinicalDecisionSteps: [
      { step: 1, action: 'Administer PHQ-9 and GAD-7', status: 'pending' },
      { step: 2, action: 'If PHQ-9 < 10 and symptoms correlate with cycle: Attribute to perimenopause', status: 'conditional' },
      { step: 3, action: 'If PHQ-9 ≥ 10: Consider MDD comorbid with perimenopause', status: 'conditional' },
      { step: 4, action: 'Trial HRT first — reassess mood at 6-week follow-up', status: 'recommended' },
      { step: 5, action: 'If mood symptoms persist after HRT: Adjust SSRI or add therapy', status: 'contingent' },
    ],
  },
  {
    diagnosis: 'Generalized Anxiety Disorder (Exacerbation)',
    icd10: 'F41.1',
    likelihoodRatio: 1.8,
    confidenceInterval: '1.0 - 3.2',
    aiConfidence: 85,
    reasoning: 'Patient has history of anxiety disorder (2018, managed). Current symptoms could represent exacerbation, though hormone-related anxiety is more likely given timing.',
    
    symptomIncidence: [
      { symptom: 'Excessive worry', patientHas: true, incidence: 94, note: 'Some worry about symptoms reported' },
      { symptom: 'Restlessness', patientHas: true, incidence: 76, note: 'Present' },
      { symptom: 'Fatigue', patientHas: true, incidence: 82, note: 'Present' },
      { symptom: 'Difficulty concentrating', patientHas: true, incidence: 78, note: 'Present' },
      { symptom: 'Irritability', patientHas: true, incidence: 74, note: 'Prominent symptom' },
      { symptom: 'Sleep disturbance', patientHas: true, incidence: 88, note: 'Present' },
      { symptom: 'Muscle tension', patientHas: false, incidence: 72, note: 'Not prominently reported' },
      { symptom: 'Palpitations', patientHas: true, incidence: 62, note: 'Present — prompted urgent care visit' },
    ],
    
    supportingEvidence: [
      { type: 'history', text: 'Diagnosed anxiety disorder (2018)' },
      { type: 'symptom', text: 'Palpitations, restlessness, worry' },
      { type: 'symptom', text: 'Sleep disruption' },
    ],
    againstEvidence: [
      { type: 'medication', text: 'Previously well-controlled on current SSRI dose' },
      { type: 'pattern', text: 'New symptom cluster began with hormone changes' },
      { type: 'pattern', text: 'Anxiety symptoms cyclical, not constant' },
    ],
    
    assessmentCriteria: {
      ruleIn: [
        { criterion: 'GAD-7 score ≥ 10', status: 'not assessed', description: 'Formal screening needed' },
        { criterion: 'Symptoms present most days for 6+ months', status: 'unclear', description: 'Recent exacerbation vs new onset unclear' },
        { criterion: 'Symptoms not better explained by another condition', status: 'not met', description: 'Perimenopause likely explanatory' },
      ],
      ruleOut: [
        { criterion: 'Symptoms better explained by medical condition', status: 'likely', description: 'Hormone-related anxiety more probable' },
        { criterion: 'Current treatment was previously effective', status: 'met', description: 'SSRI controlled symptoms until recent months' },
      ],
    },
    
    recommendedWorkup: [
      { test: 'GAD-7', priority: 'high', rationale: 'Quantify current anxiety severity' },
      { test: 'Review medication timing', priority: 'medium', rationale: 'Ensure compliance and timing consistent' },
    ],
    
    clinicalDecisionSteps: [
      { step: 1, action: 'Administer GAD-7', status: 'pending' },
      { step: 2, action: 'If GAD-7 elevated: Distinguish primary GAD exacerbation vs hormone-related anxiety', status: 'conditional' },
      { step: 3, action: 'Trial HRT — often resolves hormone-related anxiety', status: 'recommended' },
      { step: 4, action: 'If anxiety persists after HRT: Consider SSRI dose increase', status: 'contingent' },
    ],
  },
];

// Recommended assessments
const recommendedAssessments = [
  {
    category: 'Pre-Visit (Complete)',
    items: [
      { name: 'TSH + Free T4', type: 'lab', status: 'pending', priority: 'high', rationale: 'Rule out thyroid — results expected before visit' },
      { name: 'Review AI pattern analysis', type: 'review', status: 'complete', priority: 'high', rationale: '4 patterns identified across visit history' },
      { name: 'Review personal baselines', type: 'review', status: 'complete', priority: 'high', rationale: 'Multiple values changed from patient\'s normal' },
    ]
  },
  {
    category: 'During Visit — Assessment',
    items: [
      { name: 'Menstrual history', type: 'assessment', questions: ['LMP?', 'Cycle length changes?', 'Flow changes?', 'Spotting?'], priority: 'high' },
      { name: 'Vasomotor assessment', type: 'assessment', questions: ['Hot flashes?', 'Night sweats?', 'Sleep quality details?'], priority: 'high' },
      { name: 'PHQ-9 / GAD-7', type: 'assessment', questions: ['Formal mood screening given symptoms'], priority: 'high' },
      { name: 'Cognitive concerns', type: 'assessment', questions: ['Word-finding?', 'Memory?', 'Concentration?', 'Impact on work?'], priority: 'high' },
    ]
  },
  {
    category: 'During Visit — Physical',
    items: [
      { name: 'Thyroid exam', type: 'physical', priority: 'high', rationale: 'Palpate for nodules, goiter' },
      { name: 'Breast exam', type: 'physical', priority: 'high', rationale: 'Baseline before HRT, family history' },
      { name: 'Cardiovascular', type: 'physical', priority: 'medium', rationale: 'Given palpitations, HR above baseline' },
    ]
  },
  {
    category: 'Consider Ordering',
    items: [
      { name: 'Mammogram', type: 'imaging', priority: 'high', rationale: 'Required before HRT initiation given family Hx' },
      { name: 'DEXA scan', type: 'imaging', priority: 'medium', rationale: 'Baseline bone density — family Hx osteoporosis + declining estrogen' },
      { name: 'Genetic counseling referral', type: 'referral', priority: 'medium', rationale: 'BRCA discussion given first-degree relative with breast cancer' },
    ]
  },
];

// Plan of care
const initialPlanItems = [
  { id: 1, category: 'medication', text: 'Begin low-dose transdermal estradiol 0.025mg patch, twice weekly', rationale: 'First-line for vasomotor, sleep, cognitive, and mood symptoms. Transdermal preferred for CV safety. May also help musculoskeletal symptoms per AI pattern analysis.', mdApproved: true, ptApproved: null, ptComment: null },
  { id: 2, category: 'medication', text: 'Add micronized progesterone 100mg nightly', rationale: 'Required with estrogen for uterine protection. Evening dosing may help sleep.', mdApproved: true, ptApproved: null, ptComment: null },
  { id: 3, category: 'test', text: 'Complete thyroid panel (TSH, Free T4)', rationale: 'Rule out thyroid dysfunction. Compare to patient baseline (TSH 1.8).', mdApproved: true, ptApproved: true, ptComment: null },
  { id: 4, category: 'imaging', text: 'Mammogram before initiating HRT', rationale: 'Required baseline given family history. Last mammogram 18 months ago.', mdApproved: true, ptApproved: null, ptComment: 'I had one 18 months ago - is that recent enough?' },
  { id: 5, category: 'referral', text: 'Genetic counseling for BRCA testing consideration', rationale: 'First-degree relative with breast cancer warrants discussion.', mdApproved: true, ptApproved: false, ptComment: 'I\'m not sure I want to know. Can we discuss this more?' },
  { id: 6, category: 'followup', text: 'Follow-up visit in 6 weeks to assess HRT response', rationale: 'Early follow-up to titrate dose if needed, assess tolerability, review symptoms.', mdApproved: true, ptApproved: null, ptComment: 'Can we do a video visit instead?' },
  { id: 7, category: 'lifestyle', text: 'Continue symptom tracking in app', rationale: 'Objective data to assess treatment response. Will compare to current baseline.', mdApproved: true, ptApproved: true, ptComment: null },
];

// ============ REUSABLE COMPONENTS (defined outside to prevent re-render issues) ============

const Card = ({ title, children, style = {}, headerAction }) => (
  <div style={{ backgroundColor: colors.card, borderRadius: '12px', border: `1px solid ${colors.border}`, overflow: 'hidden', ...style }}>
    {title && (
      <div style={{ padding: '14px 18px', borderBottom: `1px solid ${colors.border}`, display: 'flex', justifyContent: 'space-between', alignItems: 'center' }}>
        <h3 style={{ margin: 0, fontSize: '14px', fontWeight: '600', color: colors.text }}>{title}</h3>
        {headerAction}
      </div>
    )}
    <div style={{ padding: '18px' }}>{children}</div>
  </div>
);

const Badge = ({ children, variant = 'default', size = 'normal' }) => {
  const variants = {
    default: { bg: colors.divider, color: colors.textMuted },
    success: { bg: '#DCFCE7', color: '#166534' },
    warning: { bg: '#FEF3C7', color: '#92400E' },
    error: { bg: '#FEE2E2', color: '#991B1B' },
    info: { bg: '#DBEAFE', color: '#1E40AF' },
    pending: { bg: '#FEF3C7', color: '#92400E' },
    accent: { bg: '#FDE8E0', color: '#9A4F2E' },
  };
  const v = variants[variant];
  return (
    <span style={{ 
      padding: size === 'small' ? '2px 6px' : '4px 10px', 
      backgroundColor: v.bg, 
      color: v.color, 
      borderRadius: '4px', 
      fontSize: size === 'small' ? '10px' : '11px', 
      fontWeight: '600' 
    }}>
      {children}
    </span>
  );
};

const ProgressBar = ({ value, max = 100, color = colors.primary, height = 8 }) => (
  <div style={{ width: '100%', height, backgroundColor: colors.divider, borderRadius: height / 2, overflow: 'hidden' }}>
    <div style={{ width: `${(value / max) * 100}%`, height: '100%', backgroundColor: color, borderRadius: height / 2 }} />
  </div>
);

const MiniSparkline = ({ data, color = colors.primary }) => {
  const max = Math.max(...data.map(d => d.value));
  const min = Math.min(...data.map(d => d.value));
  const range = max - min || 1;
  const width = 80;
  const height = 24;
  
  const points = data.map((d, i) => {
    const x = (i / (data.length - 1)) * width;
    const y = height - ((d.value - min) / range) * height;
    return `${x},${y}`;
  }).join(' ');
  
  return (
    <svg width={width} height={height} style={{ display: 'block' }}>
      <polyline fill="none" stroke={color} strokeWidth="2" points={points} />
    </svg>
  );
};

const Sidebar = ({ activeTab, setActiveTab }) => (
  <div style={{ width: '260px', backgroundColor: colors.sidebar, padding: '20px 0', display: 'flex', flexDirection: 'column', height: '100vh', position: 'fixed', left: 0, top: 0 }}>
    <div style={{ padding: '0 20px 24px', borderBottom: `1px solid ${colors.primaryDark}` }}>
      <h1 style={{ margin: 0, fontSize: '20px', fontWeight: '700', color: 'white' }}>PeriHealth</h1>
      <p style={{ margin: '4px 0 0', fontSize: '12px', color: colors.sidebarText }}>Clinical Decision Support</p>
    </div>
    
    <div style={{ padding: '16px', borderBottom: `1px solid ${colors.primaryDark}` }}>
      <div style={{ padding: '14px', backgroundColor: 'rgba(59, 130, 246, 0.1)', borderRadius: '10px', border: '1px solid rgba(59, 130, 246, 0.2)' }}>
        <p style={{ margin: 0, fontSize: '11px', color: colors.sidebarText }}>Current Patient</p>
        <p style={{ margin: '4px 0 0', fontSize: '15px', fontWeight: '600', color: 'white' }}>{patientData.name}</p>
        <p style={{ margin: '4px 0 0', fontSize: '12px', color: colors.sidebarText }}>{patientData.age}yo F • {patientData.mrn}</p>
        <div style={{ marginTop: '10px', padding: '6px 10px', backgroundColor: 'rgba(212, 137, 106, 0.2)', borderRadius: '6px' }}>
          <p style={{ margin: 0, fontSize: '11px', color: colors.accent }}>⚡ 4 AI patterns detected</p>
        </div>
      </div>
    </div>
    
    <nav style={{ flex: 1, padding: '16px 12px', overflowY: 'auto' }}>
      {[
        { id: 'overview', icon: '📋', label: 'Patient Overview' },
        { id: 'history', icon: '📅', label: 'Visit History & Patterns' },
        { id: 'labs', icon: '🧪', label: 'Labs & Baselines' },
        { id: 'risk', icon: '⚠️', label: 'Risk Assessment' },
        { id: 'differential', icon: '🔬', label: 'Differential Dx' },
        { id: 'prep', icon: '📝', label: 'Visit Preparation' },
        { id: 'plan', icon: '✅', label: 'Plan of Care' },
      ].map(item => (
        <button key={item.id} onClick={() => setActiveTab(item.id)} style={{
          width: '100%', padding: '12px 14px', marginBottom: '4px', border: 'none', borderRadius: '8px', cursor: 'pointer',
          backgroundColor: activeTab === item.id ? colors.sidebarActive : 'transparent',
          color: activeTab === item.id ? 'white' : colors.sidebarText,
          display: 'flex', alignItems: 'center', gap: '12px', fontSize: '13px', fontWeight: activeTab === item.id ? '600' : '400', textAlign: 'left',
        }}>
          <span style={{ fontSize: '16px' }}>{item.icon}</span>
          {item.label}
        </button>
      ))}
    </nav>
    
    <div style={{ padding: '16px', borderTop: `1px solid ${colors.primaryDark}` }}>
      <div style={{ display: 'flex', alignItems: 'center', gap: '12px' }}>
        <div style={{ width: '40px', height: '40px', borderRadius: '50%', backgroundColor: colors.primary, display: 'flex', alignItems: 'center', justifyContent: 'center', color: 'white', fontSize: '14px', fontWeight: '600' }}>SC</div>
        <div>
          <p style={{ margin: 0, fontSize: '14px', color: 'white' }}>Dr. Sarah Chen</p>
          <p style={{ margin: '2px 0 0', fontSize: '11px', color: colors.sidebarText }}>OB-GYN, Menopause Specialist</p>
        </div>
      </div>
    </div>
  </div>
);

// ============ MAIN COMPONENT ============

export default function MDDashboardV2() {
  const [activeTab, setActiveTab] = useState('overview');
  const [planItems, setPlanItems] = useState(initialPlanItems);
  const [mdNotes, setMdNotes] = useState('');
  const [expandedDx, setExpandedDx] = useState(0);
  const [expandedLab, setExpandedLab] = useState(null);
  const [expandedPattern, setExpandedPattern] = useState(null);
  const [showResponseModal, setShowResponseModal] = useState(null);
  const [responseText, setResponseText] = useState('');
  const [showVisitDetail, setShowVisitDetail] = useState(null);
  const [dxDetailView, setDxDetailView] = useState(null);

  // ============ TAB CONTENT RENDERERS ============

  const renderHistoryTab = () => (
    <div style={{ display: 'grid', gridTemplateColumns: '1.5fr 1fr', gap: '24px' }}>
      <div style={{ display: 'flex', flexDirection: 'column', gap: '20px' }}>
        <Card title="Visit History" headerAction={<span style={{ fontSize: '12px', color: colors.textMuted }}>{patientData.visitHistory.length} visits</span>}>
          <div style={{ display: 'flex', flexDirection: 'column', gap: '12px' }}>
            {patientData.visitHistory.map((visit, i) => (
              <div 
                key={i} 
                onClick={() => setShowVisitDetail(showVisitDetail === i ? null : i)}
                style={{ 
                  padding: '14px', 
                  backgroundColor: showVisitDetail === i ? `${colors.primary}08` : colors.divider, 
                  borderRadius: '10px', 
                  cursor: 'pointer',
                  border: showVisitDetail === i ? `1px solid ${colors.primary}` : '1px solid transparent',
                }}
              >
                <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'flex-start', marginBottom: '8px' }}>
                  <div>
                    <div style={{ display: 'flex', alignItems: 'center', gap: '8px', marginBottom: '4px' }}>
                      <Badge variant={
                        visit.type === 'Lab Work' ? 'info' : 
                        visit.type === 'Telehealth' ? 'success' : 
                        visit.type === 'Urgent Care' ? 'error' :
                        visit.type === 'Physical Therapy' ? 'accent' :
                        visit.type === 'Specialist' ? 'warning' :
                        visit.type === 'Dental' ? 'default' :
                        'default'
                      }>{visit.type}</Badge>
                      <span style={{ fontSize: '12px', color: colors.textMuted }}>{visit.department}</span>
                    </div>
                    <p style={{ margin: 0, fontSize: '14px', fontWeight: '500', color: colors.text }}>{visit.reason}</p>
                  </div>
                  <div style={{ textAlign: 'right' }}>
                    <p style={{ margin: 0, fontSize: '13px', fontWeight: '600', color: colors.text }}>{visit.date}</p>
                    <p style={{ margin: '2px 0 0', fontSize: '11px', color: colors.textMuted }}>{visit.provider}</p>
                  </div>
                </div>
                
                {showVisitDetail === i && (
                  <div style={{ marginTop: '12px', paddingTop: '12px', borderTop: `1px solid ${colors.border}` }}>
                    <p style={{ margin: '0 0 8px', fontSize: '11px', fontWeight: '600', color: colors.textMuted }}>FINDINGS</p>
                    {visit.findings.map((f, j) => (
                      <p key={j} style={{ margin: '4px 0', fontSize: '12px', color: colors.text }}>• {f}</p>
                    ))}
                    {visit.plan && (
                      <>
                        <p style={{ margin: '12px 0 8px', fontSize: '11px', fontWeight: '600', color: colors.textMuted }}>PLAN</p>
                        {visit.plan.map((p, j) => (
                          <p key={j} style={{ margin: '4px 0', fontSize: '12px', color: colors.text }}>• {p}</p>
                        ))}
                      </>
                    )}
                    {visit.outcome && (
                      <div style={{ marginTop: '12px', padding: '8px 12px', backgroundColor: '#DCFCE7', borderRadius: '6px' }}>
                        <p style={{ margin: 0, fontSize: '12px', color: '#166534' }}>✓ Outcome: {visit.outcome}</p>
                      </div>
                    )}
                    {visit.aiTags && (
                      <div style={{ marginTop: '12px', display: 'flex', flexWrap: 'wrap', gap: '6px' }}>
                        {visit.aiTags.map((tag, j) => (
                          <span key={j} style={{ padding: '3px 8px', backgroundColor: '#DBEAFE', color: '#1E40AF', borderRadius: '4px', fontSize: '10px' }}>🤖 {tag}</span>
                        ))}
                      </div>
                    )}
                  </div>
                )}
              </div>
            ))}
          </div>
        </Card>
      </div>

      {/* AI Patterns */}
      <div style={{ display: 'flex', flexDirection: 'column', gap: '20px' }}>
        <Card title="AI-Detected Patterns" headerAction={<Badge variant="accent">4 patterns</Badge>}>
          <p style={{ margin: '0 0 16px', fontSize: '12px', color: colors.textMuted }}>
            Cross-visit analysis found these clinically significant patterns:
          </p>
          {patientData.aiPatterns.map((pattern, i) => (
            <div 
              key={i} 
              onClick={() => setExpandedPattern(expandedPattern === i ? null : i)}
              style={{ 
                padding: '14px', 
                backgroundColor: expandedPattern === i ? `${colors.accent}08` : colors.divider, 
                borderRadius: '10px', 
                marginBottom: '12px',
                border: expandedPattern === i ? `1px solid ${colors.accent}` : '1px solid transparent',
                cursor: 'pointer',
              }}
            >
              <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'flex-start' }}>
                <div>
                  <h4 style={{ margin: '0 0 4px', fontSize: '14px', fontWeight: '600', color: colors.text }}>{pattern.title}</h4>
                  <p style={{ margin: 0, fontSize: '12px', color: colors.textMuted }}>{pattern.description}</p>
                </div>
                <div style={{ display: 'flex', alignItems: 'center', gap: '8px' }}>
                  <Badge variant={pattern.severity === 'moderate' ? 'warning' : 'default'}>{pattern.confidence}% conf</Badge>
                  <span style={{ color: colors.textMuted }}>{expandedPattern === i ? '▼' : '▶'}</span>
                </div>
              </div>
              
              {expandedPattern === i && (
                <div style={{ marginTop: '14px', paddingTop: '14px', borderTop: `1px solid ${colors.border}` }}>
                  <div style={{ marginBottom: '12px' }}>
                    <p style={{ margin: '0 0 6px', fontSize: '11px', fontWeight: '600', color: colors.textMuted }}>CONNECTED VISITS</p>
                    {pattern.connectedVisits.map((v, j) => (
                      <p key={j} style={{ margin: '3px 0', fontSize: '12px', color: colors.text }}>• {v}</p>
                    ))}
                  </div>
                  <div style={{ marginBottom: '12px' }}>
                    <p style={{ margin: '0 0 6px', fontSize: '11px', fontWeight: '600', color: colors.textMuted }}>LAB CORRELATION</p>
                    <p style={{ margin: 0, fontSize: '12px', color: colors.text }}>{pattern.labCorrelation}</p>
                  </div>
                  <div style={{ padding: '12px', backgroundColor: '#FEF3C7', borderRadius: '8px', marginBottom: '12px' }}>
                    <p style={{ margin: '0 0 4px', fontSize: '11px', fontWeight: '600', color: '#92400E' }}>💡 INSIGHT</p>
                    <p style={{ margin: 0, fontSize: '12px', color: '#78350F', lineHeight: '1.5' }}>{pattern.insight}</p>
                  </div>
                  <div style={{ padding: '12px', backgroundColor: '#DBEAFE', borderRadius: '8px' }}>
                    <p style={{ margin: '0 0 4px', fontSize: '11px', fontWeight: '600', color: '#1E40AF' }}>⚕️ CLINICAL IMPLICATION</p>
                    <p style={{ margin: 0, fontSize: '12px', color: '#1E3A5F', lineHeight: '1.5' }}>{pattern.clinicalImplication}</p>
                  </div>
                </div>
              )}
            </div>
          ))}
        </Card>
      </div>
    </div>
  );

  const renderLabsTab = () => (
    <div style={{ display: 'flex', flexDirection: 'column', gap: '24px' }}>
      {/* Legend */}
      <Card>
        <div style={{ display: 'flex', alignItems: 'center', gap: '24px', flexWrap: 'wrap' }}>
          <div style={{ display: 'flex', alignItems: 'center', gap: '8px' }}>
            <div style={{ width: '12px', height: '12px', backgroundColor: colors.success, borderRadius: '2px' }} />
            <span style={{ fontSize: '12px', color: colors.textMuted }}>Within patient's baseline</span>
          </div>
          <div style={{ display: 'flex', alignItems: 'center', gap: '8px' }}>
            <div style={{ width: '12px', height: '12px', backgroundColor: colors.warning, borderRadius: '2px' }} />
            <span style={{ fontSize: '12px', color: colors.textMuted }}>Deviating from baseline</span>
          </div>
          <div style={{ display: 'flex', alignItems: 'center', gap: '8px' }}>
            <div style={{ width: '12px', height: '12px', backgroundColor: colors.alert, borderRadius: '2px' }} />
            <span style={{ fontSize: '12px', color: colors.textMuted }}>Significantly abnormal</span>
          </div>
          <div style={{ display: 'flex', alignItems: 'center', gap: '8px' }}>
            <span style={{ fontSize: '12px', color: colors.primary, fontWeight: '600' }}>Population WNL</span>
            <span style={{ fontSize: '12px', color: colors.textMuted }}>vs</span>
            <span style={{ fontSize: '12px', color: colors.accent, fontWeight: '600' }}>Patient Baseline</span>
          </div>
        </div>
      </Card>

      {/* Hormone Panel */}
      <Card title="Hormone Panel" headerAction={<Badge variant="warning">Multiple deviations from baseline</Badge>}>
        <div style={{ display: 'flex', flexDirection: 'column', gap: '16px' }}>
          {patientData.labs.hormones.map((lab, i) => (
            <div 
              key={i} 
              onClick={() => setExpandedLab(expandedLab === `hormone-${i}` ? null : `hormone-${i}`)}
              style={{ 
                padding: '16px', 
                backgroundColor: expandedLab === `hormone-${i}` ? `${colors.primary}05` : colors.divider, 
                borderRadius: '10px',
                border: lab.baselineStatus === 'below' || lab.baselineStatus === 'above' 
                  ? `2px solid ${colors.warning}` 
                  : `1px solid ${colors.border}`,
                cursor: 'pointer',
              }}
            >
              <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center' }}>
                <div style={{ display: 'flex', alignItems: 'center', gap: '16px' }}>
                  <div>
                    <h4 style={{ margin: 0, fontSize: '15px', fontWeight: '600', color: colors.text }}>{lab.name}</h4>
                    <p style={{ margin: '4px 0 0', fontSize: '12px', color: colors.textMuted }}>
                      Ref: {lab.refRange} {lab.unit}
                    </p>
                  </div>
                </div>
                
                <div style={{ display: 'flex', alignItems: 'center', gap: '24px' }}>
                  {/* Current value */}
                  <div style={{ textAlign: 'center' }}>
                    <p style={{ margin: 0, fontSize: '11px', color: colors.textMuted }}>Current</p>
                    <p style={{ 
                      margin: '2px 0 0', 
                      fontSize: '20px', 
                      fontWeight: '700', 
                      color: lab.wnlStatus === 'high' || lab.wnlStatus === 'low' ? colors.alert : colors.text 
                    }}>
                      {lab.value}
                    </p>
                    <Badge variant={lab.wnlStatus === 'normal' ? 'success' : lab.wnlStatus === 'low-normal' ? 'warning' : 'error'} size="small">
                      {lab.wnlStatus}
                    </Badge>
                  </div>
                  
                  {/* Sparkline */}
                  {lab.history && <MiniSparkline data={lab.history} color={lab.trend === 'declining' ? colors.alert : lab.trend === 'rising' ? colors.warning : colors.success} />}
                  
                  {/* Baseline comparison */}
                  <div style={{ textAlign: 'center', padding: '8px 12px', backgroundColor: '#FDE8E0', borderRadius: '8px' }}>
                    <p style={{ margin: 0, fontSize: '11px', color: colors.accent }}>Patient Baseline</p>
                    <p style={{ margin: '2px 0 0', fontSize: '16px', fontWeight: '600', color: '#9A4F2E' }}>{lab.baseline}</p>
                    <p style={{ margin: '2px 0 0', fontSize: '10px', color: '#B85C3A' }}>
                      {lab.deviation > 0 ? '+' : ''}{lab.deviation}%
                    </p>
                  </div>
                  
                  <span style={{ color: colors.textMuted }}>{expandedLab === `hormone-${i}` ? '▼' : '▶'}</span>
                </div>
              </div>
              
              {expandedLab === `hormone-${i}` && (
                <div style={{ marginTop: '16px', paddingTop: '16px', borderTop: `1px solid ${colors.border}` }}>
                  <div style={{ display: 'grid', gridTemplateColumns: '1fr 1fr', gap: '16px', marginBottom: '16px' }}>
                    <div>
                      <p style={{ margin: '0 0 8px', fontSize: '11px', fontWeight: '600', color: colors.textMuted }}>POPULATION REFERENCE</p>
                      <p style={{ margin: 0, fontSize: '13px', color: colors.text }}>
                        Range: <strong>{lab.refRange} {lab.unit}</strong>
                      </p>
                      <p style={{ margin: '4px 0 0', fontSize: '13px', color: colors.text }}>
                        Status: <Badge variant={lab.wnlStatus === 'normal' ? 'success' : 'warning'}>{lab.wnlStatus}</Badge>
                      </p>
                    </div>
                    <div>
                      <p style={{ margin: '0 0 8px', fontSize: '11px', fontWeight: '600', color: colors.accent }}>PATIENT BASELINE</p>
                      <p style={{ margin: 0, fontSize: '13px', color: colors.text }}>
                        Typical range: <strong>{lab.baselineRange} {lab.unit}</strong>
                      </p>
                      <p style={{ margin: '4px 0 0', fontSize: '13px', color: colors.text }}>
                        Status: <Badge variant={lab.baselineStatus === 'normal' ? 'success' : 'warning'}>{lab.baselineStatus} baseline</Badge>
                      </p>
                    </div>
                  </div>
                  
                  <div style={{ marginBottom: '16px' }}>
                    <p style={{ margin: '0 0 8px', fontSize: '11px', fontWeight: '600', color: colors.textMuted }}>TREND HISTORY</p>
                    <div style={{ display: 'flex', gap: '12px' }}>
                      {lab.history.map((h, j) => (
                        <div key={j} style={{ textAlign: 'center', padding: '8px 12px', backgroundColor: colors.card, borderRadius: '6px', border: `1px solid ${colors.border}` }}>
                          <p style={{ margin: 0, fontSize: '10px', color: colors.textMuted }}>{h.date}</p>
                          <p style={{ margin: '2px 0 0', fontSize: '14px', fontWeight: '600', color: colors.text }}>{h.value}</p>
                        </div>
                      ))}
                    </div>
                  </div>
                  
                  {lab.insight && (
                    <div style={{ padding: '12px', backgroundColor: '#FEF3C7', borderRadius: '8px' }}>
                      <p style={{ margin: 0, fontSize: '12px', color: '#78350F', lineHeight: '1.5' }}>
                        💡 <strong>Clinical Insight:</strong> {lab.insight}
                      </p>
                    </div>
                  )}
                </div>
              )}
            </div>
          ))}
        </div>
      </Card>

      {/* Metabolic Panel */}
      <Card title="Metabolic Panel" headerAction={<Badge variant="info">Baseline comparison available</Badge>}>
        <div style={{ display: 'grid', gridTemplateColumns: 'repeat(2, 1fr)', gap: '12px' }}>
          {patientData.labs.metabolic.map((lab, i) => (
            <div key={i} style={{ 
              padding: '14px', 
              backgroundColor: colors.divider, 
              borderRadius: '8px',
              border: lab.baselineStatus && lab.baselineStatus !== 'normal' ? `2px solid ${colors.warning}` : 'none',
            }}>
              <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'flex-start', marginBottom: '8px' }}>
                <div>
                  <p style={{ margin: 0, fontSize: '13px', fontWeight: '500', color: colors.text }}>{lab.name}</p>
                  <p style={{ margin: '2px 0 0', fontSize: '11px', color: colors.textMuted }}>Ref: {lab.refRange}</p>
                </div>
                <div style={{ textAlign: 'right' }}>
                  <p style={{ margin: 0, fontSize: '18px', fontWeight: '700', color: lab.wnlStatus === 'borderline' ? colors.warning : colors.text }}>
                    {lab.value} <span style={{ fontSize: '12px', fontWeight: '400' }}>{lab.unit}</span>
                  </p>
                  {lab.baseline && (
                    <p style={{ margin: '2px 0 0', fontSize: '11px', color: colors.accent }}>
                      Baseline: {lab.baseline}
                    </p>
                  )}
                </div>
              </div>
              {lab.insight && (
                <div style={{ padding: '8px', backgroundColor: '#FEF3C7', borderRadius: '6px' }}>
                  <p style={{ margin: 0, fontSize: '11px', color: '#78350F' }}>{lab.insight}</p>
                </div>
              )}
            </div>
          ))}
        </div>
      </Card>

      {/* Thyroid */}
      <Card title="Thyroid Panel" headerAction={<Badge variant="pending">Pending</Badge>}>
        <div style={{ display: 'flex', gap: '16px' }}>
          {patientData.labs.thyroid.map((lab, i) => (
            <div key={i} style={{ flex: 1, padding: '16px', backgroundColor: colors.divider, borderRadius: '8px' }}>
              <p style={{ margin: 0, fontSize: '14px', fontWeight: '500', color: colors.text }}>{lab.name}</p>
              <p style={{ margin: '4px 0 0', fontSize: '12px', color: colors.textMuted }}>Ref: {lab.refRange}</p>
              <p style={{ margin: '8px 0 0', fontSize: '16px', fontWeight: '600', color: colors.warning }}>Pending</p>
              <p style={{ margin: '4px 0 0', fontSize: '11px', color: colors.accent }}>
                Patient baseline: {lab.baseline} {lab.unit}
              </p>
            </div>
          ))}
        </div>
        <div style={{ marginTop: '16px', padding: '12px', backgroundColor: '#DBEAFE', borderRadius: '8px' }}>
          <p style={{ margin: 0, fontSize: '12px', color: '#1E40AF' }}>
            ⏳ Results expected before visit. Will compare to patient's baseline TSH of 1.8 mIU/L (historically stable).
          </p>
        </div>
      </Card>
    </div>
  );

  // Overview Tab
  const renderOverviewTab = () => (
    <div style={{ display: 'grid', gridTemplateColumns: '1fr 1fr', gap: '24px' }}>
      <div style={{ display: 'flex', flexDirection: 'column', gap: '20px' }}>
        <Card title="Demographics & Vitals">
          <div style={{ display: 'grid', gridTemplateColumns: '1fr 1fr', gap: '12px', fontSize: '13px', marginBottom: '16px' }}>
            <div><span style={{ color: colors.textMuted }}>DOB:</span> <strong>{patientData.dob}</strong> ({patientData.age}yo)</div>
            <div><span style={{ color: colors.textMuted }}>Sex:</span> <strong>{patientData.sex}</strong></div>
            <div><span style={{ color: colors.textMuted }}>MRN:</span> <strong>{patientData.mrn}</strong></div>
            <div><span style={{ color: colors.textMuted }}>PCP:</span> <strong>{patientData.pcp}</strong></div>
          </div>
          <div style={{ display: 'grid', gridTemplateColumns: 'repeat(3, 1fr)', gap: '10px' }}>
            {Object.entries(patientData.vitals).slice(0, 6).map(([key, v]) => (
              <div key={key} style={{ 
                padding: '10px', 
                backgroundColor: v.flag ? '#FEF3C7' : colors.divider, 
                borderRadius: '8px',
                border: v.flag ? `2px solid ${colors.warning}` : 'none',
              }}>
                <p style={{ margin: 0, fontSize: '10px', color: colors.textMuted, textTransform: 'uppercase' }}>{key}</p>
                <p style={{ margin: '2px 0 0', fontSize: '16px', fontWeight: '600', color: colors.text }}>{v.value}</p>
                {v.baseline && (
                  <p style={{ margin: '2px 0 0', fontSize: '10px', color: v.flag ? colors.warning : colors.textMuted }}>
                    Baseline: {v.baseline} {v.unit || ''}
                  </p>
                )}
              </div>
            ))}
          </div>
        </Card>

        <Card title="Medical History">
          {patientData.medicalHistory.map((h, i) => (
            <div key={i} style={{ display: 'flex', justifyContent: 'space-between', padding: '8px 0', borderBottom: `1px solid ${colors.divider}` }}>
              <span style={{ fontSize: '13px', color: colors.text }}>{h.condition} ({h.year})</span>
              <Badge variant={h.status === 'Managed' ? 'info' : 'success'}>{h.status}</Badge>
            </div>
          ))}
          <div style={{ marginTop: '16px' }}>
            <p style={{ margin: '0 0 8px', fontSize: '12px', fontWeight: '600', color: colors.textMuted }}>ALLERGIES</p>
            <div style={{ display: 'flex', gap: '8px' }}>
              {patientData.allergies.map((a, i) => <Badge key={i} variant="error">{a}</Badge>)}
            </div>
          </div>
        </Card>

        <Card title="Family History">
          {patientData.familyHistory.map((f, i) => (
            <div key={i} style={{ marginBottom: '10px' }}>
              <p style={{ margin: '0 0 4px', fontSize: '12px', fontWeight: '600', color: colors.text }}>{f.relation}</p>
              <div style={{ display: 'flex', flexWrap: 'wrap', gap: '6px' }}>
                {f.conditions.map((c, j) => (
                  <span key={j} style={{ padding: '4px 8px', backgroundColor: c.includes('cancer') ? '#FEE2E2' : colors.divider, color: c.includes('cancer') ? '#991B1B' : colors.textMuted, borderRadius: '4px', fontSize: '11px' }}>{c}</span>
                ))}
              </div>
            </div>
          ))}
        </Card>
      </div>

      <div style={{ display: 'flex', flexDirection: 'column', gap: '20px' }}>
        <Card title="Chief Complaint">
          <p style={{ margin: 0, fontSize: '16px', fontWeight: '500', color: colors.text, lineHeight: '1.5' }}>
            "{patientData.chiefComplaint}"
          </p>
        </Card>

        <Card title="Patient Concerns" headerAction={<Badge variant="warning">{patientData.concerns.length} items</Badge>}>
          {patientData.concerns.map((c, i) => (
            <div key={i} style={{ padding: '12px', backgroundColor: c.priority === 'high' ? '#FEF3C7' : colors.divider, borderRadius: '8px', marginBottom: '8px', borderLeft: `4px solid ${c.priority === 'high' ? colors.warning : colors.border}` }}>
              <p style={{ margin: 0, fontSize: '13px', color: colors.text, lineHeight: '1.5' }}>{c.text}</p>
            </div>
          ))}
        </Card>

        <Card title="Tracked Symptoms" headerAction={<span style={{ fontSize: '12px', color: colors.textMuted }}>7 days</span>}>
          {patientData.trackedSymptoms.slice(0, 5).map((s, i) => (
            <div key={i} style={{ display: 'flex', alignItems: 'center', gap: '12px', marginBottom: '10px' }}>
              <div style={{ flex: 1 }}>
                <div style={{ display: 'flex', justifyContent: 'space-between', marginBottom: '4px' }}>
                  <span style={{ fontSize: '13px', color: colors.text }}>{s.symptom}</span>
                  <span style={{ fontSize: '12px', color: colors.textMuted }}>{s.frequency}/7</span>
                </div>
                <ProgressBar value={s.frequency} max={7} color={s.severity === 'severe' ? colors.alert : colors.warning} />
              </div>
              <Badge variant={s.trend === 'worsening' ? 'error' : s.trend === 'new' ? 'warning' : 'default'} size="small">{s.trend}</Badge>
            </div>
          ))}
        </Card>

        <Card title="AI Pattern Alerts" headerAction={<Badge variant="accent">4 detected</Badge>}>
          {patientData.aiPatterns.slice(0, 2).map((p, i) => (
            <div key={i} style={{ padding: '12px', backgroundColor: colors.divider, borderRadius: '8px', marginBottom: '8px' }}>
              <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: '4px' }}>
                <strong style={{ fontSize: '13px', color: colors.text }}>{p.title}</strong>
                <Badge variant="info">{p.confidence}%</Badge>
              </div>
              <p style={{ margin: 0, fontSize: '12px', color: colors.textMuted }}>{p.clinicalImplication}</p>
            </div>
          ))}
          <button onClick={() => setActiveTab('history')} style={{ width: '100%', padding: '10px', backgroundColor: colors.primary, color: 'white', border: 'none', borderRadius: '6px', fontSize: '12px', fontWeight: '600', cursor: 'pointer', marginTop: '8px' }}>
            View All Patterns →
          </button>
        </Card>
      </div>
    </div>
  );

  // Differential Tab with enhanced detail view
  const renderDifferentialTab = () => {
    // Helper for LR visualization
    const getLRColor = (lr) => {
      if (lr >= 10) return colors.success;
      if (lr >= 5) return colors.primary;
      if (lr >= 2) return colors.warning;
      return colors.textMuted;
    };
    
    const getLRLabel = (lr) => {
      if (lr >= 10) return 'Strong';
      if (lr >= 5) return 'Moderate';
      if (lr >= 2) return 'Weak';
      return 'Minimal';
    };

    const getLRBarWidth = (lr) => {
      const maxLR = Math.max(...differentialDiagnosis.map(d => d.likelihoodRatio));
      return `${(Math.log(lr + 1) / Math.log(maxLR + 1)) * 100}%`;
    };

    // Detail view for a single diagnosis
    if (dxDetailView !== null) {
      const dx = differentialDiagnosis[dxDetailView];
      return (
        <div style={{ display: 'flex', flexDirection: 'column', gap: '20px' }}>
          {/* Back button and header */}
          <div style={{ display: 'flex', alignItems: 'center', gap: '16px' }}>
            <button
              onClick={() => setDxDetailView(null)}
              style={{ padding: '8px 16px', backgroundColor: colors.divider, border: 'none', borderRadius: '8px', cursor: 'pointer', fontSize: '13px', color: colors.text, display: 'flex', alignItems: 'center', gap: '6px' }}
            >
              ← Back to Differential
            </button>
            {dx.ruleOut && <Badge variant="error">RULE OUT</Badge>}
          </div>

          {/* Diagnosis header */}
          <Card>
            <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'flex-start' }}>
              <div>
                <h2 style={{ margin: '0 0 4px', fontSize: '22px', fontWeight: '700', color: colors.text }}>{dx.diagnosis}</h2>
                <p style={{ margin: 0, fontSize: '13px', color: colors.textMuted }}>ICD-10: {dx.icd10}</p>
              </div>
              <div style={{ textAlign: 'right' }}>
                <div style={{ display: 'flex', alignItems: 'baseline', gap: '8px' }}>
                  <span style={{ fontSize: '36px', fontWeight: '700', color: getLRColor(dx.likelihoodRatio) }}>{dx.likelihoodRatio.toFixed(1)}</span>
                  <span style={{ fontSize: '14px', color: colors.textMuted }}>LR</span>
                </div>
                <p style={{ margin: '4px 0 0', fontSize: '12px', color: colors.textMuted }}>95% CI: {dx.confidenceInterval}</p>
                <Badge variant={getLRLabel(dx.likelihoodRatio) === 'Strong' ? 'success' : getLRLabel(dx.likelihoodRatio) === 'Moderate' ? 'info' : 'warning'}>
                  {getLRLabel(dx.likelihoodRatio)} Evidence
                </Badge>
              </div>
            </div>
            <div style={{ marginTop: '16px', padding: '12px', backgroundColor: colors.divider, borderRadius: '8px' }}>
              <p style={{ margin: 0, fontSize: '13px', color: colors.text, lineHeight: '1.6' }}>{dx.reasoning}</p>
            </div>
          </Card>

          {/* Symptom Incidence Table */}
          <Card title="Symptom Incidence" headerAction={<span style={{ fontSize: '11px', color: colors.textMuted }}>How often each symptom appears with this diagnosis</span>}>
            <div style={{ display: 'flex', flexDirection: 'column', gap: '8px' }}>
              {/* Header */}
              <div style={{ display: 'grid', gridTemplateColumns: '40px 1fr 100px 80px', gap: '12px', padding: '8px 12px', backgroundColor: colors.divider, borderRadius: '6px', fontSize: '11px', fontWeight: '600', color: colors.textMuted }}>
                <span>PT</span>
                <span>SYMPTOM</span>
                <span style={{ textAlign: 'center' }}>INCIDENCE</span>
                <span style={{ textAlign: 'right' }}>FREQ</span>
              </div>
              {/* Rows */}
              {dx.symptomIncidence.map((s, i) => (
                <div key={i} style={{ display: 'grid', gridTemplateColumns: '40px 1fr 100px 80px', gap: '12px', padding: '10px 12px', backgroundColor: s.patientHas ? `${colors.success}10` : 'transparent', borderRadius: '6px', alignItems: 'center', border: `1px solid ${s.patientHas ? colors.success : colors.border}` }}>
                  <span style={{ fontSize: '16px' }}>{s.patientHas ? '✓' : '−'}</span>
                  <div>
                    <p style={{ margin: 0, fontSize: '13px', fontWeight: '500', color: colors.text }}>{s.symptom}</p>
                    <p style={{ margin: '2px 0 0', fontSize: '11px', color: colors.textMuted }}>{s.note}</p>
                  </div>
                  <div style={{ display: 'flex', alignItems: 'center', gap: '6px' }}>
                    <div style={{ flex: 1, height: '6px', backgroundColor: colors.divider, borderRadius: '3px', overflow: 'hidden' }}>
                      <div style={{ width: `${s.incidence}%`, height: '100%', backgroundColor: s.incidence >= 80 ? colors.success : s.incidence >= 60 ? colors.primary : colors.warning, borderRadius: '3px' }} />
                    </div>
                  </div>
                  <span style={{ textAlign: 'right', fontSize: '14px', fontWeight: '600', color: s.incidence >= 80 ? colors.success : s.incidence >= 60 ? colors.primary : colors.warning }}>{s.incidence}%</span>
                </div>
              ))}
            </div>
            <div style={{ marginTop: '12px', padding: '10px', backgroundColor: '#DBEAFE', borderRadius: '6px' }}>
              <p style={{ margin: 0, fontSize: '11px', color: '#1E40AF' }}>
                <strong>PT</strong> = Patient has this symptom | <strong>Incidence</strong> = % of patients with this diagnosis who have this symptom
              </p>
            </div>
          </Card>

          {/* Two column layout for evidence and criteria */}
          <div style={{ display: 'grid', gridTemplateColumns: '1fr 1fr', gap: '20px' }}>
            {/* Supporting / Against Evidence */}
            <Card title="Clinical Evidence">
              <div style={{ marginBottom: '16px' }}>
                <p style={{ margin: '0 0 8px', fontSize: '12px', fontWeight: '600', color: '#166534' }}>✓ SUPPORTING</p>
                {dx.supportingEvidence.map((e, i) => (
                  <div key={i} style={{ display: 'flex', alignItems: 'flex-start', gap: '8px', marginBottom: '8px' }}>
                    <Badge variant={e.type === 'lab' ? 'info' : e.type === 'pattern' ? 'accent' : e.type === 'symptom' ? 'warning' : 'default'} size="small">{e.type}</Badge>
                    <span style={{ fontSize: '12px', color: colors.text, lineHeight: '1.4' }}>{e.text}</span>
                  </div>
                ))}
              </div>
              <div>
                <p style={{ margin: '0 0 8px', fontSize: '12px', fontWeight: '600', color: '#991B1B' }}>✗ AGAINST</p>
                {dx.againstEvidence.map((e, i) => (
                  <div key={i} style={{ display: 'flex', alignItems: 'flex-start', gap: '8px', marginBottom: '8px' }}>
                    <Badge variant="default" size="small">{e.type}</Badge>
                    <span style={{ fontSize: '12px', color: colors.text, lineHeight: '1.4' }}>{e.text}</span>
                  </div>
                ))}
              </div>
            </Card>

            {/* Assessment Criteria */}
            <Card title="Assessment Criteria">
              <div style={{ marginBottom: '16px' }}>
                <p style={{ margin: '0 0 10px', fontSize: '12px', fontWeight: '600', color: colors.success }}>CRITERIA TO RULE IN</p>
                {dx.assessmentCriteria.ruleIn.map((c, i) => (
                  <div key={i} style={{ padding: '10px', backgroundColor: c.status === 'met' ? '#DCFCE7' : c.status === 'likely' ? '#FEF3C7' : colors.divider, borderRadius: '6px', marginBottom: '8px', border: `1px solid ${c.status === 'met' ? '#86EFAC' : c.status === 'likely' ? '#FDE68A' : colors.border}` }}>
                    <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: '4px' }}>
                      <span style={{ fontSize: '12px', fontWeight: '600', color: colors.text }}>{c.criterion}</span>
                      <Badge variant={c.status === 'met' ? 'success' : c.status === 'likely' ? 'warning' : c.status === 'pending' ? 'pending' : 'default'} size="small">{c.status}</Badge>
                    </div>
                    <p style={{ margin: 0, fontSize: '11px', color: colors.textMuted }}>{c.description}</p>
                  </div>
                ))}
              </div>
              <div>
                <p style={{ margin: '0 0 10px', fontSize: '12px', fontWeight: '600', color: colors.alert }}>CRITERIA TO RULE OUT</p>
                {dx.assessmentCriteria.ruleOut.map((c, i) => (
                  <div key={i} style={{ padding: '10px', backgroundColor: c.status === 'met' ? '#FEE2E2' : c.status === 'likely' ? '#FEF3C7' : colors.divider, borderRadius: '6px', marginBottom: '8px', border: `1px solid ${c.status === 'met' ? '#FECACA' : c.status === 'likely' ? '#FDE68A' : colors.border}` }}>
                    <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: '4px' }}>
                      <span style={{ fontSize: '12px', fontWeight: '600', color: colors.text }}>{c.criterion}</span>
                      <Badge variant={c.status === 'met' ? 'error' : c.status === 'likely' ? 'warning' : c.status === 'pending' ? 'pending' : 'default'} size="small">{c.status}</Badge>
                    </div>
                    <p style={{ margin: 0, fontSize: '11px', color: colors.textMuted }}>{c.description}</p>
                  </div>
                ))}
              </div>
            </Card>
          </div>

          {/* Recommended Workup */}
          <Card title="Recommended Workup">
            <div style={{ display: 'grid', gridTemplateColumns: 'repeat(2, 1fr)', gap: '12px' }}>
              {dx.recommendedWorkup.map((w, i) => (
                <div key={i} style={{ padding: '14px', backgroundColor: w.priority === 'high' ? '#FEF3C7' : colors.divider, borderRadius: '8px', border: w.priority === 'high' ? `2px solid ${colors.warning}` : `1px solid ${colors.border}` }}>
                  <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: '6px' }}>
                    <span style={{ fontSize: '14px', fontWeight: '600', color: colors.text }}>{w.test}</span>
                    <Badge variant={w.priority === 'high' ? 'error' : w.priority === 'medium' ? 'warning' : 'default'} size="small">{w.priority}</Badge>
                  </div>
                  <p style={{ margin: 0, fontSize: '12px', color: colors.textMuted }}>{w.rationale}</p>
                </div>
              ))}
            </div>
          </Card>

          {/* Clinical Decision Steps */}
          <Card title="Clinical Decision Steps">
            <div style={{ display: 'flex', flexDirection: 'column', gap: '12px' }}>
              {dx.clinicalDecisionSteps.map((step, i) => (
                <div key={i} style={{ display: 'flex', gap: '14px', padding: '12px', backgroundColor: step.status === 'pending' ? colors.divider : step.status === 'recommended' ? '#DCFCE7' : '#DBEAFE', borderRadius: '8px' }}>
                  <div style={{ width: '28px', height: '28px', borderRadius: '50%', backgroundColor: step.status === 'recommended' ? colors.success : colors.primary, color: 'white', display: 'flex', alignItems: 'center', justifyContent: 'center', fontSize: '13px', fontWeight: '700', flexShrink: 0 }}>{step.step}</div>
                  <div style={{ flex: 1 }}>
                    <p style={{ margin: 0, fontSize: '13px', fontWeight: '500', color: colors.text }}>{step.action}</p>
                    {step.questions && (
                      <div style={{ marginTop: '8px', padding: '8px', backgroundColor: 'white', borderRadius: '6px' }}>
                        {step.questions.map((q, j) => <p key={j} style={{ margin: '2px 0', fontSize: '11px', color: colors.textMuted }}>• {q}</p>)}
                      </div>
                    )}
                    {step.considerations && (
                      <div style={{ marginTop: '8px', padding: '8px', backgroundColor: 'white', borderRadius: '6px' }}>
                        {step.considerations.map((c, j) => <p key={j} style={{ margin: '2px 0', fontSize: '11px', color: colors.textMuted }}>• {c}</p>)}
                      </div>
                    )}
                    {step.note && <p style={{ margin: '6px 0 0', fontSize: '11px', color: colors.primary, fontStyle: 'italic' }}>{step.note}</p>}
                  </div>
                  <Badge variant={step.status === 'pending' ? 'pending' : step.status === 'recommended' ? 'success' : step.status === 'conditional' ? 'info' : 'default'} size="small">{step.status}</Badge>
                </div>
              ))}
            </div>
          </Card>
        </div>
      );
    }

    // Summary view - list of all diagnoses
    return (
      <div style={{ display: 'flex', flexDirection: 'column', gap: '24px' }}>
        <Card title="Differential Diagnosis" headerAction={
          <div style={{ display: 'flex', gap: '12px', alignItems: 'center' }}>
            <span style={{ fontSize: '12px', color: colors.textMuted }}>Ranked by Likelihood Ratio</span>
            <Badge variant="success">AI Confidence: {differentialDiagnosis[0].aiConfidence}%</Badge>
          </div>
        }>
          <p style={{ margin: '0 0 16px', fontSize: '12px', color: colors.textMuted }}>
            Click any diagnosis to see symptom incidence, assessment criteria, and clinical decision steps.
          </p>
          {differentialDiagnosis.map((dx, i) => (
            <div 
              key={i} 
              onClick={() => setDxDetailView(i)}
              style={{ marginBottom: '12px', border: `2px solid ${i === 0 ? colors.primary : colors.border}`, borderRadius: '12px', overflow: 'hidden', cursor: 'pointer', transition: 'all 0.2s ease' }}
            >
              <div style={{ padding: '16px', backgroundColor: i === 0 ? `${colors.primary}08` : colors.card, display: 'flex', justifyContent: 'space-between', alignItems: 'center' }}>
                <div style={{ display: 'flex', alignItems: 'center', gap: '14px', flex: 1 }}>
                  <div style={{ width: '36px', height: '36px', borderRadius: '50%', backgroundColor: i === 0 ? colors.primary : colors.divider, color: i === 0 ? 'white' : colors.textMuted, display: 'flex', alignItems: 'center', justifyContent: 'center', fontSize: '16px', fontWeight: '700' }}>{i + 1}</div>
                  <div style={{ flex: 1 }}>
                    <div style={{ display: 'flex', alignItems: 'center', gap: '8px' }}>
                      <h4 style={{ margin: 0, fontSize: '16px', fontWeight: '600', color: colors.text }}>{dx.diagnosis}</h4>
                      {dx.ruleOut && <Badge variant="error">RULE OUT</Badge>}
                    </div>
                    <p style={{ margin: '2px 0 0', fontSize: '12px', color: colors.textMuted }}>ICD-10: {dx.icd10}</p>
                  </div>
                </div>
                <div style={{ display: 'flex', alignItems: 'center', gap: '20px' }}>
                  {/* LR Bar */}
                  <div style={{ width: '100px' }}>
                    <div style={{ display: 'flex', justifyContent: 'space-between', marginBottom: '4px' }}>
                      <span style={{ fontSize: '10px', color: colors.textMuted }}>{getLRLabel(dx.likelihoodRatio)}</span>
                    </div>
                    <div style={{ width: '100%', height: '6px', backgroundColor: colors.divider, borderRadius: '3px', overflow: 'hidden' }}>
                      <div style={{ width: getLRBarWidth(dx.likelihoodRatio), height: '100%', backgroundColor: getLRColor(dx.likelihoodRatio), borderRadius: '3px' }} />
                    </div>
                  </div>
                  {/* LR Value */}
                  <div style={{ textAlign: 'right', minWidth: '80px' }}>
                    <p style={{ margin: 0, fontSize: '24px', fontWeight: '700', color: getLRColor(dx.likelihoodRatio) }}>{dx.likelihoodRatio.toFixed(1)}</p>
                    <p style={{ margin: 0, fontSize: '10px', color: colors.textMuted }}>LR (CI: {dx.confidenceInterval})</p>
                  </div>
                  {/* Arrow */}
                  <span style={{ fontSize: '18px', color: colors.textMuted }}>→</span>
                </div>
              </div>
              {/* Quick preview */}
              <div style={{ padding: '12px 16px', backgroundColor: colors.divider, borderTop: `1px solid ${colors.border}`, display: 'flex', gap: '16px', flexWrap: 'wrap' }}>
                <span style={{ fontSize: '11px', color: colors.textMuted }}>
                  <strong style={{ color: colors.success }}>✓ {dx.supportingEvidence.length}</strong> supporting
                </span>
                <span style={{ fontSize: '11px', color: colors.textMuted }}>
                  <strong style={{ color: colors.alert }}>✗ {dx.againstEvidence.length}</strong> against
                </span>
                <span style={{ fontSize: '11px', color: colors.textMuted }}>
                  <strong style={{ color: colors.primary }}>{dx.symptomIncidence.filter(s => s.patientHas).length}/{dx.symptomIncidence.length}</strong> symptoms present
                </span>
                <span style={{ fontSize: '11px', color: colors.textMuted }}>
                  <strong style={{ color: colors.warning }}>{dx.recommendedWorkup.filter(w => w.priority === 'high').length}</strong> high-priority tests
                </span>
              </div>
            </div>
          ))}
        </Card>

        {/* Quick summary of pending items */}
        <Card title="Pending Items Across All Diagnoses" headerAction={<Badge variant="warning">Action Required</Badge>}>
          <div style={{ display: 'grid', gridTemplateColumns: 'repeat(3, 1fr)', gap: '12px' }}>
            <div style={{ padding: '14px', backgroundColor: '#FEF3C7', borderRadius: '8px' }}>
              <p style={{ margin: '0 0 6px', fontSize: '12px', fontWeight: '600', color: '#92400E' }}>Pending Labs</p>
              <p style={{ margin: 0, fontSize: '13px', color: '#78350F' }}>TSH + Free T4</p>
              <p style={{ margin: '4px 0 0', fontSize: '11px', color: '#92400E' }}>Required to rule out thyroid dysfunction</p>
            </div>
            <div style={{ padding: '14px', backgroundColor: '#FEF3C7', borderRadius: '8px' }}>
              <p style={{ margin: '0 0 6px', fontSize: '12px', fontWeight: '600', color: '#92400E' }}>Assessments Needed</p>
              <p style={{ margin: 0, fontSize: '13px', color: '#78350F' }}>PHQ-9, GAD-7</p>
              <p style={{ margin: '4px 0 0', fontSize: '11px', color: '#92400E' }}>Formal mood/anxiety screening</p>
            </div>
            <div style={{ padding: '14px', backgroundColor: '#FEF3C7', borderRadius: '8px' }}>
              <p style={{ margin: '0 0 6px', fontSize: '12px', fontWeight: '600', color: '#92400E' }}>Pre-Treatment</p>
              <p style={{ margin: 0, fontSize: '13px', color: '#78350F' }}>Mammogram</p>
              <p style={{ margin: '4px 0 0', fontSize: '11px', color: '#92400E' }}>Required before HRT initiation</p>
            </div>
          </div>
        </Card>
      </div>
    );
  };

  // Visit Prep Tab
  const renderPrepTab = () => (
    <div style={{ display: 'grid', gridTemplateColumns: '1fr 1fr', gap: '24px' }}>
      {recommendedAssessments.map((section, i) => (
        <Card key={i} title={section.category}>
          {section.items.map((item, j) => (
            <div key={j} style={{ padding: '12px', backgroundColor: colors.divider, borderRadius: '8px', marginBottom: '10px' }}>
              <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'flex-start', marginBottom: '6px' }}>
                <strong style={{ fontSize: '13px', color: colors.text }}>{item.name}</strong>
                <div style={{ display: 'flex', gap: '6px' }}>
                  {item.status && <Badge variant={item.status === 'complete' ? 'success' : 'pending'}>{item.status}</Badge>}
                  <Badge variant={item.priority === 'high' ? 'error' : item.priority === 'medium' ? 'warning' : 'default'}>{item.priority}</Badge>
                </div>
              </div>
              {item.rationale && <p style={{ margin: 0, fontSize: '12px', color: colors.textMuted }}>{item.rationale}</p>}
              {item.questions && (
                <div style={{ marginTop: '8px', padding: '8px', backgroundColor: colors.card, borderRadius: '6px' }}>
                  {item.questions.map((q, k) => <p key={k} style={{ margin: '2px 0', fontSize: '11px', color: colors.text }}>• {q}</p>)}
                </div>
              )}
            </div>
          ))}
        </Card>
      ))}
    </div>
  );

  // Plan Tab
  const renderPlanTab = () => (
    <div style={{ display: 'grid', gridTemplateColumns: '2fr 1fr', gap: '24px' }}>
      <div style={{ display: 'flex', flexDirection: 'column', gap: '20px' }}>
        <Card title="Plan of Care" headerAction={
          <div style={{ display: 'flex', gap: '8px' }}>
            <Badge variant="success">{planItems.filter(p => p.ptApproved === true).length} agreed</Badge>
            <Badge variant="error">{planItems.filter(p => p.ptApproved === false || p.ptComment).length} needs discussion</Badge>
          </div>
        }>
          {planItems.map((item) => (
            <div key={item.id} style={{ 
              padding: '16px', 
              border: `2px solid ${item.ptApproved === false ? colors.alert : item.ptComment ? colors.warning : colors.border}`, 
              borderRadius: '10px', 
              marginBottom: '12px',
              backgroundColor: item.ptApproved === false ? '#FEF2F2' : item.ptComment ? '#FFFBEB' : colors.card,
            }}>
              <div style={{ display: 'flex', alignItems: 'flex-start', gap: '12px', marginBottom: '8px' }}>
                <div style={{ 
                  width: '28px', height: '28px', borderRadius: '6px', 
                  backgroundColor: item.ptApproved === true ? colors.success : item.ptApproved === false ? colors.alert : colors.divider,
                  color: item.ptApproved !== null ? 'white' : colors.textMuted,
                  display: 'flex', alignItems: 'center', justifyContent: 'center', fontSize: '14px', flexShrink: 0,
                }}>
                  {item.ptApproved === true ? '✓' : item.ptApproved === false ? '✗' : '?'}
                </div>
                <div style={{ flex: 1 }}>
                  <Badge variant={item.category === 'medication' ? 'info' : item.category === 'test' ? 'warning' : item.category === 'referral' ? 'error' : 'success'}>{item.category}</Badge>
                  <p style={{ margin: '6px 0 4px', fontSize: '14px', fontWeight: '500', color: colors.text }}>{item.text}</p>
                  <p style={{ margin: 0, fontSize: '12px', color: colors.textMuted }}>{item.rationale}</p>
                </div>
              </div>
              {item.ptComment && (
                <div style={{ marginTop: '12px', padding: '12px', backgroundColor: item.ptApproved === false ? '#FEE2E2' : '#FEF3C7', borderRadius: '8px' }}>
                  <p style={{ margin: '0 0 4px', fontSize: '11px', fontWeight: '600', color: colors.textMuted }}>PATIENT COMMENT</p>
                  <p style={{ margin: 0, fontSize: '13px', color: colors.text }}>"{item.ptComment}"</p>
                  <button onClick={() => { setShowResponseModal(item.id); setResponseText(''); }} style={{ marginTop: '10px', padding: '8px 16px', backgroundColor: colors.primary, color: 'white', border: 'none', borderRadius: '6px', fontSize: '12px', fontWeight: '600', cursor: 'pointer' }}>
                    Respond to Patient
                  </button>
                </div>
              )}
            </div>
          ))}
        </Card>

        <Card title="Clinical Notes">
          <textarea value={mdNotes} onChange={(e) => setMdNotes(e.target.value)} placeholder="Document clinical reasoning, shared decision-making discussion, patient education..." style={{ width: '100%', minHeight: '120px', padding: '12px', border: `1px solid ${colors.border}`, borderRadius: '8px', fontSize: '13px', fontFamily: 'inherit', resize: 'vertical', boxSizing: 'border-box' }} />
          <div style={{ marginTop: '12px', display: 'flex', gap: '12px' }}>
            <button style={{ flex: 1, padding: '12px', backgroundColor: colors.divider, color: colors.text, border: 'none', borderRadius: '8px', fontSize: '13px', fontWeight: '600', cursor: 'pointer' }}>Save Draft</button>
            <button style={{ flex: 1, padding: '12px', backgroundColor: colors.primary, color: 'white', border: 'none', borderRadius: '8px', fontSize: '13px', fontWeight: '600', cursor: 'pointer' }}>Finalize & Send to Patient</button>
          </div>
        </Card>
      </div>

      <div style={{ display: 'flex', flexDirection: 'column', gap: '20px' }}>
        <Card title="Working Diagnosis">
          <div style={{ padding: '16px', backgroundColor: `${colors.primary}08`, borderRadius: '8px', marginBottom: '12px' }}>
            <h4 style={{ margin: 0, fontSize: '18px', fontWeight: '600', color: colors.primary }}>Perimenopause</h4>
            <p style={{ margin: '4px 0 0', fontSize: '12px', color: colors.textMuted }}>ICD-10: N95.1</p>
            <p style={{ margin: '8px 0 0', fontSize: '14px', color: colors.text }}>Confidence: <strong>92%</strong></p>
          </div>
          <div style={{ marginBottom: '12px' }}>
            <p style={{ margin: '0 0 6px', fontSize: '11px', fontWeight: '600', color: colors.textMuted }}>SUPPORTING PATTERNS</p>
            <p style={{ margin: '2px 0', fontSize: '12px', color: '#166534' }}>✓ Musculoskeletal cluster (89%)</p>
            <p style={{ margin: '2px 0', fontSize: '12px', color: '#166534' }}>✓ Metabolic shift (85%)</p>
            <p style={{ margin: '2px 0', fontSize: '12px', color: '#166534' }}>✓ CV symptom correlation (82%)</p>
          </div>
          <div>
            <p style={{ margin: '0 0 6px', fontSize: '11px', fontWeight: '600', color: colors.textMuted }}>PENDING</p>
            <p style={{ margin: '2px 0', fontSize: '12px', color: colors.warning }}>⏳ Thyroid panel</p>
          </div>
        </Card>

        <Card title="Patient Collaboration Status">
          <div style={{ display: 'flex', flexDirection: 'column', gap: '8px' }}>
            <div style={{ padding: '10px', backgroundColor: '#DCFCE7', borderRadius: '6px' }}>
              <p style={{ margin: 0, fontSize: '11px', color: '#166534' }}>Agreed</p>
              <p style={{ margin: '2px 0 0', fontSize: '18px', fontWeight: '600', color: '#166534' }}>{planItems.filter(p => p.ptApproved === true).length} items</p>
            </div>
            <div style={{ padding: '10px', backgroundColor: '#FEE2E2', borderRadius: '6px' }}>
              <p style={{ margin: 0, fontSize: '11px', color: '#991B1B' }}>Needs Discussion</p>
              <p style={{ margin: '2px 0 0', fontSize: '18px', fontWeight: '600', color: '#991B1B' }}>{planItems.filter(p => p.ptApproved === false || p.ptComment).length} items</p>
            </div>
            <div style={{ padding: '10px', backgroundColor: colors.divider, borderRadius: '6px' }}>
              <p style={{ margin: 0, fontSize: '11px', color: colors.textMuted }}>Pending Review</p>
              <p style={{ margin: '2px 0 0', fontSize: '18px', fontWeight: '600', color: colors.text }}>{planItems.filter(p => p.ptApproved === null && !p.ptComment).length} items</p>
            </div>
          </div>
        </Card>
      </div>

      {showResponseModal && (
        <div style={{ position: 'fixed', top: 0, left: 0, right: 0, bottom: 0, backgroundColor: 'rgba(0,0,0,0.5)', display: 'flex', alignItems: 'center', justifyContent: 'center', zIndex: 1000 }}>
          <div style={{ backgroundColor: 'white', borderRadius: '12px', padding: '24px', width: '500px', maxWidth: '90%' }}>
            <h3 style={{ margin: '0 0 16px', fontSize: '18px', color: colors.text }}>Respond to Patient</h3>
            <div style={{ padding: '12px', backgroundColor: colors.divider, borderRadius: '8px', marginBottom: '16px' }}>
              <p style={{ margin: 0, fontSize: '13px', color: colors.text }}>"{planItems.find(p => p.id === showResponseModal)?.ptComment}"</p>
            </div>
            <textarea value={responseText} onChange={(e) => setResponseText(e.target.value)} placeholder="Type your response..." style={{ width: '100%', minHeight: '100px', padding: '12px', border: `1px solid ${colors.border}`, borderRadius: '8px', fontSize: '13px', fontFamily: 'inherit', marginBottom: '16px', boxSizing: 'border-box' }} />
            <div style={{ display: 'flex', gap: '12px' }}>
              <button onClick={() => setShowResponseModal(null)} style={{ flex: 1, padding: '12px', backgroundColor: colors.divider, color: colors.text, border: 'none', borderRadius: '8px', fontSize: '13px', fontWeight: '600', cursor: 'pointer' }}>Cancel</button>
              <button onClick={() => { alert('Response sent!'); setShowResponseModal(null); }} style={{ flex: 1, padding: '12px', backgroundColor: colors.primary, color: 'white', border: 'none', borderRadius: '8px', fontSize: '13px', fontWeight: '600', cursor: 'pointer' }}>Send Response</button>
            </div>
          </div>
        </div>
      )}
    </div>
  );

  // Risk Tab
  const renderRiskTab = () => (
    <Card title="Risk Assessment">
      <p style={{ color: colors.textMuted }}>See Labs & Baselines and Visit History tabs for risk factor analysis integrated with patient data.</p>
    </Card>
  );

  const renderTab = () => {
    switch (activeTab) {
      case 'overview': return renderOverviewTab();
      case 'history': return renderHistoryTab();
      case 'labs': return renderLabsTab();
      case 'risk': return renderRiskTab();
      case 'differential': return renderDifferentialTab();
      case 'prep': return renderPrepTab();
      case 'plan': return renderPlanTab();
      default: return renderOverviewTab();
    }
  };

  return (
    <div style={{ fontFamily: '-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif', backgroundColor: colors.surface, minHeight: '100vh' }}>
      <Sidebar activeTab={activeTab} setActiveTab={setActiveTab} />
      <div style={{ marginLeft: '260px', padding: '24px' }}>
        <div style={{ display: 'flex', justifyContent: 'space-between', alignItems: 'center', marginBottom: '24px' }}>
          <div>
            <h2 style={{ margin: 0, fontSize: '24px', fontWeight: '700', color: colors.text }}>
              {activeTab === 'overview' && 'Patient Overview'}
              {activeTab === 'history' && 'Visit History & AI Patterns'}
              {activeTab === 'labs' && 'Labs & Personal Baselines'}
              {activeTab === 'risk' && 'Risk Assessment'}
              {activeTab === 'differential' && 'Differential Diagnosis'}
              {activeTab === 'prep' && 'Visit Preparation'}
              {activeTab === 'plan' && 'Plan of Care'}
            </h2>
            <p style={{ margin: '4px 0 0', fontSize: '14px', color: colors.textMuted }}>
              {patientData.name} • {patientData.visitType} • {patientData.appointmentDate}
            </p>
          </div>
          <div style={{ display: 'flex', gap: '12px' }}>
            <button style={{ padding: '10px 20px', backgroundColor: 'white', color: colors.primary, border: `2px solid ${colors.primary}`, borderRadius: '8px', fontSize: '13px', fontWeight: '600', cursor: 'pointer' }}>Print Summary</button>
            <button style={{ padding: '10px 20px', backgroundColor: colors.primary, color: 'white', border: 'none', borderRadius: '8px', fontSize: '13px', fontWeight: '600', cursor: 'pointer' }}>Start Visit</button>
          </div>
        </div>
        {renderTab()}
      </div>
    </div>
  );
}
