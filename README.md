🏥 EMRBots: Privacy-Preserving Healthcare Data Framework with Federated Learning
📌 Overview

EMRBots is a complete end-to-end framework for secure, privacy-preserving healthcare data processing and analytics. It integrates:

📊 Data ingestion & preprocessing
🔐 Data anonymization using advanced diversity constraints (DiVA-based models)
🛡️ Privacy architecture (encryption + secure communication)
🤝 Federated Learning (FL) for distributed model training
📡 Real-time IoT simulation & messaging (Kafka + MQTT)
📈 Evaluation and visualization
🖥️ Web-based dashboard and UI

This system is designed for Electronic Medical Records (EMR) environments to ensure compliance with data privacy, scalability, and utility preservation.

📂 Repository Structure
EMRBots/
│
├── Datasets_Sample/
├── Manuscript_Images/
├── Source Code/
│   ├── 1_data_pipeline/
│   ├── 2_data_anonymization/
│   ├── 3_privacy_architecture/
│   ├── 4_federated_learning/
│   ├── 5_integration/
│   ├── 6_evaluation/
│   ├── 7_application_simulation/
│   ├── 8_user_interface/
│   └── 9_security_logging/
📊 Datasets
1. EMR Patients Dataset (Synthetic Healthcare Data)

This dataset simulates hospital EMR records.

Files
AdmissionsCorePopulatedTable.txt
AdmissionsDiagnosesCorePopulatedTable.txt
PatientCorePopulatedTable.txt
Attribute Details
Patient Table
PatientID: Unique identifier
Gender: Male/Female
DateOfBirth: Patient birth date
Race: Ethnicity
MaritalStatus
Language
Admissions Table
AdmissionID
PatientID
AdmissionDate
DischargeDate
AdmissionType
HospitalUnit
Diagnoses Table
DiagnosisCode
DiagnosisDescription
SeverityLevel
2. Breast Cancer Dataset (WDBC)

Files:

wdbc.data
wdbc.names
Attribute Details
ID: Patient ID
Diagnosis: M (Malignant), B (Benign)
Features (30 attributes):
Radius, Texture, Perimeter, Area
Smoothness, Compactness
Concavity, Symmetry
Fractal Dimension
3. IoT Healthcare Dataset

Located in:

1_data_pipeline/iot_data/
Attributes
sensor_id
timestamp
heart_rate
blood_pressure
oxygen_level
temperature
🔐 Diversity Constraints

Diversity constraints are used in anonymization to ensure fair distribution and privacy.

Format
attrName(attrValue)[lower_bound, upper_bound]
Example
Gender(Male) [100, 500]
Gender(Female) [100, 500]

Diagnosis(Cancer) [50, 200]
Diagnosis(Diabetes) [50, 200]
Diversity Constraints Applied
1. EMR Dataset
Minimum
Gender(Male) [1, N]
Gender(Female) [1, 1]
Average
Gender(Male) [N/2, N/2]
Gender(Female) [N/2, N/2]
Proportion
Gender(Male) [70%, 70%]
Gender(Female) [30%, 30%]
2. IoT Dataset
sensor_type(HeartRate) [100, 500]
sensor_type(Temperature) [100, 500]
3. WDBC Dataset
Diagnosis(Malignant) [200, 300]
Diagnosis(Benign) [200, 300]
⚙️ Source Code Modules
1️⃣ Data Pipeline

Handles ingestion, preprocessing, and metadata.

preprocess/Preprocess.txt
metadata/metadata.txt
iot_data/iot data.txt
Features
Missing value handling
Data normalization
Schema generation
2️⃣ Data Anonymization (DiVA Framework)

Directory:

2_data_anonymization/diva/
Files
diva.py
diva_anonymity.py
diva_opt1.py, diva_opt2.py
hash_generation.py
hierarchy_to_tree.py
Features
k-anonymity
l-diversity
t-closeness
Optimization strategies
3️⃣ Privacy Architecture
Encryption
aes_encryption.py
Communication
tls_communication.py
Features
AES-based encryption
TLS-secured communication
Secure data exchange
4️⃣ Federated Learning
Aggregation
fedavg.py
Nodes
client_node.py
Secure Aggregation
secure_sum.py
Features
Decentralized training
Privacy-preserving updates
Secure model aggregation
5️⃣ Integration Layer
Kafka
kafka_producer.py
kafka_consumer.py
MQTT
mqtt_publisher_client.py
mqtt_subscriber_server.py
mqtt_broker_sim.py
Features
Real-time data streaming
Distributed communication
6️⃣ Evaluation
Files
evaluate_centralized.py
evaluate_federated.py
evaluation_metrics.py
Metrics
Accuracy
Precision
Recall
F1-score
Information Loss
Execution Time
7️⃣ Application Simulation
Files
dashboard.py
health_predictor.py
data_simulator.py
Features
Real-time alerts
Health prediction
Simulation environment
8️⃣ User Interface
Frontend
React (App.js, index.js)
Backend
Flask (flask_app/)
Components
UploadForm.js
AnonymizationViewer.js
Features
Dataset upload
Visualization dashboard
Anonymization viewer
9️⃣ Security Logging
Files
security_logger.py
anomaly_detector.py
logger_config.py
Features
Intrusion detection
Log monitoring
Threat analysis
📈 Results & Visualizations

Located in:

Manuscript_Images/
Includes
Block Diagram
Data Flow Diagram
Information Loss Analysis
Execution Time Analysis
Scalability Analysis
🔄 Workflow
Data Collection
Preprocessing
Anonymization (DiVA)
Encryption
Federated Learning
Evaluation
Visualization
🚀 How to Run
Step 1: Install Dependencies
pip install -r requirements.txt
Step 2: Run Data Pipeline
python preprocess.py
Step 3: Run Anonymization
python diva.py
Step 4: Start Federated Learning
python client_node.py
python fedavg.py
Step 5: Launch UI
cd flask_app
python app.py
🧠 Key Contributions
✅ Privacy-preserving EMR framework
✅ Advanced DiVA anonymization
✅ Secure federated learning
✅ Real-time IoT integration
✅ Full-stack implementation
📚 Applications
Smart Healthcare Systems
Remote Patient Monitoring
Medical Research
Privacy-Aware AI Systems
