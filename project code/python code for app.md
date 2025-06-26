import pandas as pd
from sklearn.ensemble import RandomForestClassifier
from sklearn.preprocessing import StandardScaler
from sklearn.model_selection import train_test_split
import pickle

# Step A: Load and clean the data
df = pd.read_csv("liver_data.csv")
df = df.dropna()
df['Gender']=df['Gender'].map({'Male':1,'Female':0})
df['Dataset'] = df['Dataset'].map({1: 0, 2: 1})

X = df.drop("Dataset", axis=1)
y = df["Dataset"]

# Step B: Scale the features
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)
pickle.dump(scaler, open("normalizer.pkl", "wb"))

# Step C: Train the model
X_train, X_test, y_train, y_test = train_test_split(X_scaled, y, test_size=0.2)
model = RandomForestClassifier()
model.fit(X_train, y_train)

# Step D: Save the model
pickle.dump(model, open("rf_acc_68.pkl", "wb"))
