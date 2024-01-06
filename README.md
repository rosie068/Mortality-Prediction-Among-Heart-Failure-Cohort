# Predicting In-Hospital Mortality Among Patients Admitted with a Diagnosis of Heart Failure: A Machine Learning Approach

Here we include the pipeline for training, testing and validating machine learning models to predict mortality at least 12 hours before event in patients admitted with a heart failure diagnosis. If you would like further details, see the paper below; if you use the code, please cite it.

> Predicting In-Hospital Mortality Among Patients Admitted with a Diagnosis of Heart Failure: A Machine Learning Approach  
> Zina Jawadi, Rosemary He, Pratyaksh K. Srivastava, Gregg C. Fonarow, Suzan O. Khalil, Srikanth Krishnan, Eleazar Eskin, Jeffrey N. Chiange, Ali Nsair 
> will add link here

## Data preprocessing
In compliance with HIPPA, we will not be sharing our data or pre-processing scripts with sensitive information, but will provide a toy example dataset and describe the input format below. For input, we take in the following:
  1. HospitalAdmissionTime: for splitting the dataset into train and test, user can define their own timepoint or use random split as they see fit
  2. ExpiredStatus: target value for patient mortality
  3. Demographics: PatientAge, PatientBMI, Sex(binary), SmokingStatus(binary), Race(binned groups), ef_category(binned groups)
  4. Comorbidity: past diagnosis based on ICD-9/10 codes, binary variables. Ex. Cardiactransplant, NotCardiacTransplant, Aortic Valve Disorders, Atrial Fibrillation/Atrial Flutter, Cerebrovascular Disease Including Ischemic/Hemorrhagic Stroke.
  5. Vitals: Four on admission values: BPSystolicAtPresentation, BPDiastolicAtPresentation, PulseAtPresentation, TemperatureAtPresentation. Five vital measures split into 5 timepoints relative to the hospital stay length: Heart_Rate, SpO2, Temperature, Systolic_bp, Diastolic_bp. The post fix _0, _1, _2, _3, _4 represents the value closest to the xth quater time of the entire stay.
  7. Labs: Five labs recorded once: CHOL, CHOLHDL, CHOLLDL, HGBA1C, TRIGLY and respective _missing columns to indicate missingness. The rest of lab measures, eg. BNP, Calcium, HGB, Creatine, split into 5 timepoints similar to vitals, and a _missing column.


All measures within 12-hr window prior to event have been removed. The example.csv file serves merely as an example of input data.


