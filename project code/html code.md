<!DOCTYPE html>
<html>
<head>
  <title>Liver Cirrhosis Prediction</title>
</head>
<body>
  <h2>Liver Cirrhosis Prediction Form</h2>
  <form action="/predict" method="POST">
    <label>Age:</label><input type="number" name="Age" required><br><br>
    <label>Gender:</label>
    <select name="Gender">
      <option value="1">Male</option>
      <option value="0">Female</option>
    </select><br><br>
    <label>Total Bilirubin:</label><input type="number" step="any" name="Total_Bilirubin" required><br><br>
    <label>Direct Bilirubin:</label><input type="number" step="any" name="Direct_Bilirubin" required><br><br>
    <label>Alkaline Phosphotase:</label><input type="number" name="Alkaline_Phosphotase" required><br><br>
    <label>Alamine Aminotransferase:</label><input type="number" name="Alamine_Aminotransferase" required><br><br>
    <label>Aspartate Aminotransferase:</label><input type="number" name="Aspartate_Aminotransferase" required><br><br>
    <label>Total Proteins:</label><input type="number" step="any" name="Total_Proteins" required><br><br>
    <label>Albumin:</label><input type="number" step="any" name="Albumin" required><br><br>
    <label>Albumin and Globulin Ratio:</label><input type="number" step="any" name="Albumin_and_Globulin_Ratio" required><br><br>
    
    <button type="submit">Predict</button>
  </form>
    {%if prediction_text %}
         <h3>prediction:  {{prediction_text }}</h3>
    {% endif %}
</body>
</html>
