## Water Quality Analysis and Modeling 

For my project, I have decided to use machine learning to investigate how to analyze and model water quality. 

***

## Introduction 

Water is essential to health, poverty reduction, food security, ecosystems and education.
Accessibility to water resources and potable water is a necessity as well as a global issue for many people worldwide. Water quality analysis is crucial for public health, environmental conservation and sustainable resource management. It is fundamental in ensuring the safety of drinking water as it can help identify the presence of harmful substances such as pollutants, bacteria and contaminants.  Compliance with established water quality standards is central to providing safe and potable drinking water to communities. Ensuring that water is free from contaminants is vital for public health, especially because waterborne diseases such as cholera and dysentery can spread through contaminated water sources. Many countries around the world, most notably low-income countries, rely on nearby water sources such as streams or lakes and drink directly from these sources. According to the United Nations, in 2022, it was reported that 2.2 billion people lacked safe portable water and sanitation stations. With climate change and water pollution, more countries are facing challenges in safely managing their water resources with extreme weather leading to water scarcity and the degradation of water ecosystems. 
 
With changing climate dynamics and feedback systems within the water cycle, it has become increasingly challenging to assess and manage water resources. Creating a water quality model to predict safe drinking water and distinguish portable water could inform the public about what water source is safest to drink from. Determining the most important feature in measuring water quality using machine learning could also reduce the process in keeping track of each variable and help the decision-making for communities to switch their water sources.

## Data

For this project, I will base my model on a public domain dataset found on Kaggle that contains water quality metrics for 3,276 different water bodies throughout the world:
https://www.kaggle.com/datasets/adityakadiwal/water-potability

Within this dataset, there are nine variables to determine if water would be portable and safe drinking. The following variables are: 
1. pH value: (0 - 14)
pH is an indicator of acidic or alkaline water conditions. The World Health Organization has recommended the pH of water to be within a range of 6.5 to 8.5. 
2. Hardness: (mg/L)
Hardness of water is caused by calcium and magnesium salts, which are dissolved from deposits when water travels. Thus, it is defined as the capacity of water to precipitate soap.
3. Total Dissolved Solids: (mg/L)
Since water has the ability to dissolve various inorganic and organic minerals, these minerals have the ability to produce harsh tasting water and dilute the clarity of water. This parameter is important to figuring out the use of water such as drinking, personal hygiene and agricultural use. For drinking purposes, a range of 500 mg/L to 1,000 mg/L. 
4. Chloramines: (mg/L)
Chlorine and chloramine are major disinfectants in the treatment of water. Acceptable chlorine levels are 4 mg/L for drinking water.  
5. Sulfate: (mg/L)
Sulfates can be found in soil and minerals, which makes its way into water sources. Chemical industries are also known to release sulfates into nearby water resources. Thus, a sulfate concentration of 3 mg/L to 30 mg/L is relatively common in freshwater systems considered safe to drink. 
6. Conductivity: (μS/cm)
Drinkable water should not be a good conductor of electricity and should act as a good insulator. The World Health Organization has recommended values near 400 μS/cm for drinking purposes. 
7. Organic Carbon: (ppm)
Decaying natural organic matter created organic carbon within water resources. This decaying matter is a good indicator of possible bacteria and diseases within the water. According to the Environment Protection Agency, the typical value in treated water from wastewater treatment plants and drinking water is less than 2 ppm. 
8. Trihalomethanes: (μg/L)
Trihalomethanes is usually found in drinking water that was treated with chlorine. The concentrations of THMs vary depending on the concentration of organic matter. A maximum THM concentration of 80 μg/L is considered safe in drinking water. 
9. Turbidity: (NTU)
Turbidity of water greatly depends on the quantity of dissolved solids, minerals and suspended material within the water. The recommended value is about 5 NTU according to the World Health Organization. 

This dataset includes a category (Potability) that determines if the water was considered portable or not. A value of 1 indicates that the water is portable and a value of 0 indicates that that water is not potable.

To prepare the dataset for modeling, the dataset was first uploaded to Google Drive and loaded onto a Google Colab Notebook. I used the pandas library to load the csv file as a dataframe object. After this, I found any missing data or invalid values within the dataset. There were 491 invalid pH values, 781 invalid sulfate values and 162 invalid trihalomethanes values. I calculated the mean and median values for the numeric pH, sulfate and trihalomethanes values found within the dataset. Comparing the mean and median values for potable and non-potable water, it could be seen that there were small differences between the mean and median values (Figure 1). Thus, it was decided to use the median values to replace the invalid values since it is not sensitive to outliers, if any are present within the dataset. Shown in Figure 2 is a visual representing the amount of samples that are considered to be potable and non-potable.

![](assets/IMG/datapenguin.png){: width="500" }

*Figure 1: Here is a caption for my diagram. This one shows a pengiun [1].*

## Modelling

Here are some more details about the machine learning approach, and why this was deemed appropriate for the dataset. 

The model might involve optimizing some quantity. You can include snippets of code if it is helpful to explain things.

```python
from sklearn.ensemble import ExtraTreesClassifier
from sklearn.datasets import make_classification
X, y = make_classification(n_features=4, random_state=0)
clf = ExtraTreesClassifier(n_estimators=100, random_state=0)
clf.fit(X, y)
clf.predict([[0, 0, 0, 0]])
```

This is how the method was developed.

## Results

Figure X shows... [description of Figure X].

## Discussion

From Figure X, one can see that... [interpretation of Figure X].

## Conclusion

Here is a brief summary. From this work, the following conclusions can be made:
1. first conclusion
* second conclusion

Here is how this work could be developed further in a future project.

## References
[1] DALL-E 3

[back](./)

