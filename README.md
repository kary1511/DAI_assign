# DAI_assign
# Titanic Dataset Cleaning & Analysis  
**By Kartikey Pal (23116041)**  

## Introduction  
The Titanic dataset provides insights into passenger demographics, travel details, and survival rates. This report analyzes the dataset to identify patterns and trends in survival probabilities based on different features.  

##  Dataset Overview  
- **Total Records:** 891 passengers  
- **Target Feature:** `survived` (0 = No, 1 = Yes)  
- **Feature Categories:**  
  - **Demographic Information:** `sex`, `age`, `who`, `adult_male`  
  - **Social & Economic Factors:** `pclass`, `fare`, `class`  
  - **Travel Details:** `embarked`, `alone`, `sibsp`, `parch`  
  - **Survival Indicators:** `survived`, `alive`, `deck`  

## Data Cleaning  
### Handling Missing Values  
- `age`: 20% missing → Filled with median (29.36 years)  
- `deck`: 77% missing → Dropped due to excessive missingness  
- `embarked` & `embark_town`: 2 missing → Imputed using mode (`S`)  

### Duplicate Removal  
- **107 duplicate rows** detected and removed  

### Outliers  
- **`age` & `fare`** had extreme values but were retained as they represent valid cases.  

##  Data Distribution Analysis  
### Demographics  
- **Gender:** 62% male, 38% female  
- **Age Distribution:** Mean = **29.4 years**, majority aged **21–36**  
- **Passenger Categories:** 57% men, 32% women, 11% children  

### Economic & Class Insights  
- **Class Proportions:**  
  - 52% Third Class  
  - 27% First Class  
  - 21% Second Class  
- **Fare Statistics:**  
  - Mean = **£26.6**  
  - Highly skewed; **75% of fares ≤ £34.2**  

### Survival Rate  
- **Overall Survival:** **41.3%**  
- **Survived vs. Deceased:** 59% perished, 41% survived  

### Embarkation Details  
- **Majority Embarked from:**  
  - 72% Southampton  
  - 20% Cherbourg  
  - 8% Queenstown  
- **Solo Travelers:** 60% of passengers traveled alone  

## Factors Affecting Survival  
### **Survival by Gender**  
Women and children had significantly higher survival rates than men.  
The `who` column confirms gender-based survival disparity.  

### **Survival by Class**  
First-Class passengers had the highest survival rate.  

### **Fare Influence**  
✅ Higher fares correlate with better survival chances, as wealthier passengers had priority access to lifeboats.  

### **Impact of Age**  
✅ Younger passengers had better survival rates, but missing data limits precision.  

## 📈 Statistical Insights  
- **Skewness & Distribution:**  
  - `sibsp` (skew = 3.0) and `parch` (skew = 2.6) → Most passengers traveled alone.  
  - `fare` is right-skewed → High ticket price variability.  
- **Correlation Trends:**  
  - **Negative correlation** between `pclass` and `survived`  
  - **Positive correlation** between `fare` and `survived`  

## Key Visualizations & Trends  
(Visualizations assumed based on analysis)  
- **Class vs. Survival:** Higher-class passengers had better survival rates.  
- **Gender vs. Survival:** Women outlived men significantly.  
- **Age Distribution:** Peaks at childhood (0–10) and adulthood (20–40).  
- **Fare & Survival:** Expensive tickets linked to survival.  

## Challenges & Limitations  
- **Data Gaps:** High missing values in `deck`, some in `age`.  
- **Duplicate Removal:** May remove passengers from the same group.  
- **Outliers:** Extreme values for `fare` and `age` retained but could affect modeling.  
- **Categorical Encoding:** Features like `embarked`, `who`, and `class` need transformation for ML models.  

## Suggested Enhancements  
### **Feature Engineering**  
Create `family_size = sibsp + parch`  
Bin `age` into categories (`child`, `adult`, `senior`)  
Encode categorical features for predictive modeling  

### **Predictive Modeling**  
Apply **logistic regression** or **decision trees** for survival prediction  
Use `pclass`, `sex`, `fare`, and `age` as key predictors  

### **Further Research**  
Investigate the impact of `embark_town`  
Examine the effects of traveling **alone vs. with family**  

## Final Thoughts  
- **Women, children, and First-Class passengers had the highest survival rates.**  
- **High fares and embarkation from Cherbourg correlate with survival.**  
- **Age and family size are important secondary factors.**  
- **Future Direction:** Develop a **predictive model** and validate findings with hypothesis testing (e.g., chi-square for categorical relationships).  










