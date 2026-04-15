# Project Tittle
### APPLICATION OF VECTOR AUTOREGRESSION (VAR) FORMODELING AND PREDICTING THE DYNAMIC RELATIONSHIP BETWEEN AVERAGE RAINFALL AND WETNESS IN CHANGING CLIMATIC CONDITIONS


# Executive Summary
Rainfall and wetness are fundamental climatic variables that influence agriculture, water
management, and environmental sustainability. Understanding their interdependence is
essential to improve weather forecasting, flood risk assessment, and climate adaptation
strategies. This study employs a vector autoregression model (VAR) to analyze the dy
namic relationship between average rainfall and wetness over time. By investigating the
lag structure between these variables, the research improves the predictive precision, pro
viding deeper insights into how past rainfall patterns influence future wetness levels.
The dataset, obtained from secondary sources, contains missing values, which were han
dled using interpolation techniques. Time series visualization, trend analysis, and sta
tionality tests were performed to ensure robust modeling. The optimal lag order was
determined using the Akaike Information Criterion (AIC), and the fitted VAR model
was assessed by diagnostic checks, including serial correlation tests and Granger causal
ity analysis. Forecasting and impulse response functions further illustrate the extent to
which rainfall fluctuations affect wetness levels over time.
The findings of this study contribute to improving climate modeling and weather pre
diction systems, helping decision makers in sectors such as agriculture, hydrology, and
disaster preparedness. Using data-driven insights, this research highlights the importance
of understanding climate variability for sustainable resource management.

# 1. About 
This project explores the dynamic relationship between rainfall and surface wetness using a Vector Autoregression (VAR) model within the context of climate change. As global climate variability intensifies, understanding how rainfall influences wetness over time is critical for improving agricultural productivity, water resource management, and environmental sustainability. Focusing on Ghana's  Central Region, the study highlights how irregular rainfall patterns—characterized by major and minor rainy seasons—affect soil moisture, crop yields, and livelihoods. These impacts are particularly significant in agriculture-dependent communities and coastal areas vulnerable to flooding and ecosystem changes.

Traditional hydrological models often fail to capture the non-linear and time-lagged interactions between rainfall and wetness. This project addresses that gap by applying VAR modeling, which allows for the analysis of interdependencies and temporal dynamics between variables.

#### The findings aim to support:

i. Climate-smart agriculture
ii. Improved flood prediction and water management
iii. Data-driven decision-making for climate resilience

Overall, this project demonstrates how advanced statistical modeling can enhance understanding of climate-driven processes and contribute to sustainable development strategies.

# 1.1 Tools 
- Excel
- R
# Liberies 
library(vars)  For fiting a Vector Autoregression model
library(tseries)Tests for stationarity 
library(tidyverse) For selecting rows based on conditions
library(stargazer) For creating tables 
library(ggplot2) Fpr creating plots
library(forecast) For generating future predictions
library(imputeTS) Handling Missing Values

# 1.2 Objective of the Study
#### Main objective
Understanding the dynamic relationship between rainfall and wetness is essential for
improving climate modeling, weather forecasting, and resource management. This study
seeks to explore this interdependence through statistical modeling and predictive analysis.

#### Specific objectives are:
• Toexamine the dynamic effects of shocks in average monthly rainfall on the number
of wet days, and vice versa, using impulse response analysis.
• To determine the optimal lag length for the VAR model that best captures the
relationship between average monthly rainfall and the number of wet days from
2019 to 2024 in the Central Region.
• Toinvestigate the direction and existence of Granger causality between rainfall and
wet days, assessing whether one can be used to predict the other.
• To evaluate the forecasting performance of the fitted VAR model in predicting av
erage monthly rainfall and the number of wet days for the next 6 months, including
estimation of prediction intervals.

# 1.3 Scope of this Study
This study aims to investigate the dynamic relationship between average rainfall and
the number of wet days within the Central Region of Ghana, Vector Autoregression
(VAR) model is being used in this our study. The study focus on the Central Region
Ghana only, leveraging meteorological data sourced from stations within the areas of
the Central Region Ghana between 2019 to 2024 using monthly to capture the relevant
climatic patterns. The analysis will focus solely on the variables of average rainfall and
the number of wet days, although there are other climatic factors existing in the Central
Region Ghana but are outside the primary focus of this research.

# 1.4 Significance of study
In this study, forecasting by the traditional method (ARIMA) may not fully capture the lag effects and the interdependence between rainfall and wetness. By using the Vector Autoregression (VAR), which captures the mutual impact of these variables over time,this study sets to develop a predictive model that seeks to improve forecasting accuracy and analyzes the inter-dependences between average rainfall and wetness over time in the Central Region of Ghana. These insights can be valuable to the climate scientists,8 meteorologist and hydrologist working to improve climate modeling in similar regions. Accurate predictions of wetness levels based on rainfall data are vital for agriculture and water conservation efforts, as the study provides information that can assist farmers and water resource managers in optimizing water usage, reducing drought vulnerability, and improving flood risk assessments. The study findings may encourage broader adoption of the Vector Autoregression for studying other climate related variables, such as temperature, humidity, evaporation.
# 1.5 Methodology
This study applies a Vector Autoregression (VAR) model to analyze the relationship
between rainfall and wetness over time. The statistical software used for the data analysisis R. The dataset is preprocessed, interpolating missing values and converting it into a time-series format. Trend analysis (Mann-Kendall test) and stationarity checks (ADF, PP, and KPSS test) are performed, with differencing applied if necessary. The optimal lag order is selected using AIC, and a VAR model is fitted. Granger causality tests assess predictive relationships, while diagnostic checks ensure model validity. The model forecasts 6 months ahead, and accuracy is evaluated using RMSE. Impulse Response Function (IRF) analysis examines how rainfall shocks impact wetness over time.

# 1.6 Limitation of the Study
The limitations of this project stem primarily from data quality issues, as it relies on secondary data with missing values, which were handled using interpolation. This may introduce biases and reduce accuracy. Additionally, the assumption of stationarity, tested using the Augmented Dickey Fuller (ADF) test, may overlook nonlinear trends, while lag selection based on AIC could lead to overfitting or underfitting. The Granger causality test identifies predictive relationships rather than true causation, limiting the depth of causal inference. Forecasting accuracy is also constrained by the linear assumptions of the VAR model, making it less effective for capturing complex climate interactions. Moreover, the analysis does not account for external factors such as climate change, land use changes, or geographical variations, which may influence rainfall and wetness patterns. Despite these limitations, the study provides valuable insights, and future improvements could incorporate nonlinear models and additional climatic variables for enhanced predictive accuracy.

# 2 LITERATURE REVIEW
## 2.1 Introduction
The objective of this chapter is to review the theoretical and empirical literature that explains the implementation of a VAR model to analyze the relationship between variables essential to the study. Numerous similar studies have looked into how government spending influence economic growth. Numerous economic theories have been explored in the theoretical literature to explain how government expenditure influences economic growth. Wefindthis study very interesting because it departs from the aim of predicting economic variables, which is certainly an important, but not the only conceivable task of time series
modeling. Although specific studies focusing on VAR models to analyze the relationship between rainfall and wet days are scarce, the existing literature underscores the model’s capability to handle multivariate time series data in climatology, health and many more. Given that wet days are closely related to rainfall patterns, applying VAR could provide insight into their dynamic inter-dependencies. This chapter presents a comprehensive review of existing literature relevant to the modeling with Vector Autoregression as well as predicting the inter-dependencies in wetness and rainfaill. It begins by examining conceptual framework on rainfall, wetness and VAR models. A review of previous study where VAR model is used on various variables such as economic, health and others is then provided. This section also highlights gabs, associated in our review and lastly the need for us to conduct this study. 

## 2.2 Conceptual Review of Rainfall and Wetness
Rainfall and wetness are two fundamental hydro-meteorological variables that play a vital role in environmental monitoring, agricultural productivity, and water resource management. Rainfall refers to the total precipitation usually measured in millimeters received over a particular period. It serves as a primary input to surface and subsurface hydrological systems, influencing soil moisture levels, groundwater recharge, and vegetation growth.Research across Ghana’s agro-ecological zones indicates varying trend in rainfall and wetness. Owusu (2009) found that there’s increasing trend in annual rainfall totals in the Savannah and Forest zones, while the Coastal and Transition zones showed decreasing trend.
Rainfall plays an important role in determining the production of food crops in the
Central regions of Ghana and Africa, as large. This is a region, characterized by two
distinct rainfalls. A major and minor variable distribution of rainfall spatially and over time, which constitutes a limiting potential for crop yields (Tesfaye et al. 2004; Graef et al., 2001). The major season runs from April to July, and the minor season runs from September to November. Rainfall amount normally range from 800 mm to 1500mm annually, with the costal areas receiving least amount, according to the ministry of Food and Agriculture (MOFA).
Wetness, on the other hand, can be described in various ways, often involving indicators such as the number of wet days (days with rainfall exceeding a certain threshold), soil moisture content, or surface wetness indices derived from meteorological data. The number of wet days is particularly important as it captures not only the quantity but also the frequency and temporal distribution of rainfall events. A region may receive significant total rainfall concentrated in a few days, or moderate rainfall spread over many days both of which have different implications for agriculture, flood risk, and ecological systems. According to Nkrumah (2021), consecutive wet days (CWD) were shorter and localized, with higher duration in Birim sub-catchmemt. This spatial variability underscores the importance of localized studies in understanding wetness dynamics. The interaction between average rainfall and wetness is dynamic and complex. While rainfall is the primary driver of wetness, the temporal distribution of rainfall (i.e., how frequently it rains) can influence the persistence of wet or dry conditions on the surface. For instance, prolonged dry spells between rainy days may lead to reduced soil wetness even when average rainfall appears adequate. This study is grounded in the hypothesis that rainfall and wetness exhibit a time dependent relationship, where past values of one variable can help predict future values of the other. Understanding this interdependence is essential, particularly in the context of climate change, which is expected to alter not only the volume of rainfall but also its temporal structure. These changes can have profound effects on drought occurrence, crop cycles, and the design of water infrastructure. 
## 2.3 Conceptual Review of VAR models
The Vector Autoregression model, which was introduced by Christopher Sims in 1980,
is one of the most flexible and easy to use models for the analysis of multivariate time series.It is a natural extension of the univariate autoregressive model which aims to analyze and forecast systems where multiple interconnected variables influence each other over time. Unlike univariate autoregressive models, that focus on a single variable, Vector Autoregression model takes into consideration how each variable in a system is being affected by its own past values and the past values of all other variables in the system.
To model this interrelationship, this study employs a Vector Autoregression (VAR) model, which allows for simultaneous modeling of both variables while accounting for their mutual lagged effects. This approach aims to improve our understanding of the temporal dy namics between rainfall and wetness and how changes in rainfall influence wetness and vice versa which enhances forecasting accuracy under changing climate conditions. Forecast from VAR models are quite flexible because they can be made conditional on the potential future paths of specified variables in the model.
Understanding how rainfall and wetness interact over time is critical for predicting climate change impacts. Vector Autoregression (VAR) models provide a flexible framework to capture these dynamic relationships, accounting for feedback loops and lagged effects.
## 2.4 VAR model on Climatic Variables
Many researchers have studied the climatic variables. Ferdous and Baten (2011) used
least square method for analyzing trend of climatic data (temperature, rainfall, relative humidity, and sunshine) of Rajshahi and Rangpur Division to observe the climate variability. Shamsnia et al. (2011) used stochastic methods (autoregressive integrated moving average [ARIMA] model) for modeling of weather parameters, such as precipitation, temperature, and relative humidity. Kleiber et al. (2013) developed a bivariate stochastic model was applied to a daily temperature (minimum and maximum) data set covering the complex terrain of Colorado, USA, for studying climate impact and successfully quarters considerable temporally varying non-stationarity in both the direct-covariance and cross-covariance functions. But they didn’t study the climate variability among temperature, humidity and cloud coverage for the response of one climatic variable on the other variable. The variability study among the climatic variables is essential. VAR offers such analysis. A VAR analysis is widely used in several disciplines. Khan and Hossain (2010) used VAR model for democracy and trade balance. Altaf et al. (2012) used the VAR model for macroeconomic variables of Pakistan’s economic growth. Moneta et al.(2011) used structural VAR models for causal search. Awokuse and Bessler (2003) used VAR model to the US economy.Stergiou et al. (1997) analyzed monthly fisheries catches
using seven forecasting techniques including regression and univariate and multivariate time series methods and finally mentioned that the univariate ARIMA and multivariate dynamic regression (MDREG) and VAR time series models all predicted persistence of catches. Durban and Glasbey (2001) used the vector autoregressive moving average (VARMA) process as a model for daily weather data and selected a vector second-order autoregressive first-order moving average process, which fits the data better and produces more realistic simulated series than existing models. Mosedale et al. (2006) used bivariate VAR time series models to fit daily winter time sea surface temperatures and North Atlantic Oscillation time series produced by a 50-year simulation of the Third Hadley Centre Coupled Ocean–Atmosphere GCM (HadCM3). Wang and Niu (2009) used the VAR model for wind speeds, temperatures, soil temperatures, and dew points for Los Angeles Long Beach area. Janjua et al. (2010) used the VAR model to investigate the impact of climate change on wheat production in Pakistan and concluded that there is no significant negative impact of climate change on wheat production in Pakistan. Liu et al. (2011) used the VAR model for examining how climate problem indicates high-profile international event, and climate science feedback influence media and congressional at tention to global warming and climate change. Adenomon et al. (2013) used VAR model for analyzing dynamic relationship between time series rainfall and temperature data in
Niger state, Nigeria, and found that there exists bidirectional causation between them. So, it is needed to analyze all the interrelated variables for a better forecast on climatic data. Thus, the purpose of the present study is to develop an appropriate VAR model for a better forecasting on rainfall and wetness.

## 2.5 VAR model on Agriculture
Vector Autoregression (VAR) models are highly suitable for analyzing the complex in
terdependencies between agricultural outcomes and climate variables like rainfall and
wetness.Water is the major limiting resource for crop growth in many semi-arid regions of the world, particularly in Central Region Ghana and other sub-Saharan Africa where rainfall is limited, variable in space and time, and unpredictable (Stewart and Hash, 1982, Sivakumar, 1992). VAR model on Agricultural Variables(e.g., rainfall, soil moisture content, crop yields soil and so on) as a function on its own past values and the past values of all other variables in the system. Despite its amount, the distribution of rainfall and wetness in a given season is critical in affecting crop growth and growth yield (Monteith,1991, Simane and Struik, 1993), as uneven seasonal distribution of rainfall and wetness can expose crops to different degrees of dry spells without significant reductions in total
rainfall (Barron et al., 2003). Reductions in crop performance and yield also result from mismatches between water supply and its demand by the crop. VAR model allows re
searchers to understand how a ”shock” in rainfall is specifically the case in Ethiopia where a given crop is grown in a wide range of environments (see, e.g., Simane and Struik, 1993;Simane et al., 1998). Mismatch between the crop and its growing environment can lead either to crop failure or to under exploitation of available water.Nevertheless, recent empirical studies have yielded mixed and sometimes conflicting evidence and there remains a lack of consensus on the effect of agriculture on economic growth. While some researchers contend that agricultural development is a precondition to industrialization and economic growth, others strongly disagree and argue for a different path. Several authors assert that growth in the overall economy depends on the development of the agricultural sector (Schultz 1964; Gollin et al 2002).Early development theories viewed agriculture as an
important source of resources to finance the development of the industrial sector. VAR analysis provide several studies that provide evidence that the impact of rainfall and soil moisture (wetness) shocks on agricultural productivity exists (e.g., Chavas et al., 2005; Holden et al., 2001; Horrell and Krishnan, 2007; Kilic et al., 2015; Udry et al., 1997), research that explicitly accounts for rainfall shocks con-sidering crop-specific productivity as well as geological zones, using micro level panel datasets is still nascent. Thus, agricultural production growth could serve as an engine of growth for the overall economy. VAR analysis examines the impact of rainfall shocks on crop-specific agricultural land productivity and based on geographical zones using nationally representative panel datasets from Ghana merged with georeferenced rainfall information. In doing so, the paper pro
vides evidence on the role of farming systems and practices in coping with rainfall shock. VAR study examines a key issue relating rainfall shocks and agricultural productivity to household consumption in the presence of unobserved heterogeneity, which could cause an endogeneity problem. VAR explicitly address the potential endogeneity of agricultural productivity using exogenous rainfall shock as an instrumental variable for agricultural productivity. VAR examines the distributional implication of rainfall shocks by estimating its impact on household consumption by initial wealth tercile and geographical zone, with important implications for designing policies intended to protect livelihoods under rainfall shock. Hwa (1988). VAR model analysis the Its impact on poverty is both direct,flowing immediately from growth in agriculture by raising real incomes of poor farm (and nonfarm) households, and indirect, increasing agricultural outputs, which induces job creation in upstream and downstream nonfarm sectors as a response to higher domestic demand (Christiaensen et al., 2011; Gollin et al., 2014).Agricultural research and develop
ment interventions focused on farm intensification and modernization of market channels for agricultural products can lead to agricultural productivity growth and thereby both reduce poverty and meet growing demands for food (Fan, 2008; Loayza and Raddatz,2010; Ravallion and Datt, 1999; Thirtle et al., 2003). VAR analysis is widely used to fills a knowledge gap that exists in countries like Ghana on how rainfall shocks contributes to the relations between agricultural productivity and house-hold consumption. VAR analysis also provide information on agricultural productivity, which is expected to be simultaneously determined with household consumption, could be an endogenous decision by farm households. Agricultural productivity is also expected to be correlated with unobservable household characteristics that may affect household consumption. Thus,OLS would cause upward- or downward-biased7 estimates (Bellemare, 2013; Hausman and Taylor, 1981). More specifically, if a farmer’s agricultural productivity is measured with error, and the true value of the impact of agricultural productivity is positive, the
OLS estimate will be biased toward zero, even if that error has a mean of zero. Thus,
the OLS estimate will be too small because of attenuation bias. The two sources of bias could apply simultaneously to the OLS estimation: the upward bias caused by omitted ability variables and the downward bias caused by measurement error in agricultural productivity (Wooldridge, 2010).

## 2.6 Gaps in Literature
Despite the growing body of research addressing climatic variability and its impacts
on climate-hydrology patterns, significant gaps remain in how the relationship between rainfall and atmospheric wet days is analyzed and modeled.
Firstly, limitation in methodology are evident in the dominant use of univariate or simple statistical methods. Reseachers have largely relied on trend detection technique (such as Mann-Kendall tests), standardized precipitation index(SPI), ARIMA models or the regression-based methods to investigate the behaviour and hydrological impact of rainfall (e.g rahman et al.(2017); Sa’di et al.(2019); Koudahe et al.(2017)) .Also, Kankam-Yeboah et al.(2013) used the Soil and Water Assessment Tool(SWAT) together with climate projections from the global climate models to estimate the impact of climate change on streaflow in the White Volta and Pra river basins in Ghana but did not offer insight into the time-dependent interaction. These approaches, while useful for basic analysis, do not adequately capture the multivariate and lagged interactions between rainfall and other factors such us temperature, humidity etc.
In contrast, Vector Autoregression(VAR) has shown to offer significant advantage for
multivariate time series modeling. The VAR’s ability to account for bidirectional re
lationships and time-lagged effects has be successfully demonstrated in fields such as economics, epidemiology and others. For instance,in climate-related research, the VAR model was used successfully in modeling meteorological variables as Shahin et al.(2014),forecasted temperature, humidity and cloud coverage in Bangladesh, showing that the vector autoreegression could outperform SARIMA in peridictive accuracy. Similarly, Ankamah et al.(2018) applied Vector Autoregression in Ghana to model the impact of climate variability on Malaria,employing Grange causality and impulse response function to reveal significant lagged effects.
Furthermore, the weakness in the analysis has serious real-life effects.. Accurately modeling how anomalies in rainfall affect the frequency, duration, and clustering of wet days is essential for planning flood response systems, drought mitigation, agricultural calendars, and early-warning mechanisms. While global assessments (eg., IPCC, 2021) emphasize changing rainfall patterns, few models translate this into how many wet days follow a significant rainfall shock, or how long that effect lingers. VAR, with its strengths in lagged and bidirectional relationships, is ideally suited to answer these questions Importantly, this gap is global. VAR studies in Indonesia (Rohmawati & Gunawan, 2019,July), Nigeria (Musa & Maijamaa, 2024), Botswana (Ouma et al., 2022) and Malaysia (Rahim & Puay, 2017) focus on rainfall or other meteorological variables, but none systematically incorporate atmospheric wet-day count as a dependent variable within a multivariate VAR framework. Thus, the dynamic feedback loop between rainfall volume and wet-day persistence remains unexplored using the full suite of VAR tools.

# 3. RESEARCH METHODOLOGY


## Key Fundings 
- Data collection and preprocessing  
- Handling missing values using interpolation techniques  
- Stationarity testing (ADF test)  
- Lag selection using information criteria (AIC, BIC)  
- Estimation of VAR model  
- Diagnostic checks  
- Impulse Response Functions (IRF) and Forecast Error Variance Decomposition (FEVD)  

---

## 3.1 Introduction
This chapter discusses the statistical techniques, instruments, and the Vector Autoregression (VAR) model used in the study. Fundamental time series principles are explored, including stationarity, unit roots, lag selection, and autoregression, to ensure the robustness of the analysis. The chapter also examines spurious regression risks and applies the Augmented Dickey-Fuller (ADF) test to confirm the stationarity of the dataset.
Additionally, the Granger causality test is used to determine the direction or influence between rainfall and wetness, while the Johansen cointegration analysis is considered to assess any long-term equilibrium relationships between the two variables. The study further employs Impulse Response Functions (IRF) and forecasting techniques to analyze how shocks in rainfall impact wetness levels over time.
## 3.2 Data Source and Acquisition
The data for this research is secondary data sourced from Ghana Meteorological Services. It consists of monthly measurements of rainfall amount and wet days, recorded in millimeters (mm) over five-year period (2019–2024). Asikuma, Baako, Assin Foso, Bieni,and Asamankese in the Central Region of Ghana, are the stations the data was collected from. The dataset was obtained in Excel format and was selected for its availability and comprehensiveness, as well as its alignment with the research objective, analyzing the relationship between average rainfall and wet days over time.
The dataset includes key variables such as date, average rainfall amount, and wet days of the various stations and the averages are used. The variables are essential for conducting time series analysis and modeling. These variables enable a thorough examination of rainfall patterns and their influence on wetness, providing valuable insights for climate studies, forecasting, and resource management.

## 3.3 Research Design
The Vector autoregression (VAR) developed by Christopher A. Sims in 1980 has been
extenensively used in the econometrics for the analysis of multivariate time series. It is a powerful and flexible econometric framework designed to capture the dynamic inter relationships among time series variables. Due to overly restrictive structural models, Sims proposed the VAR model, which treats all variables as endogenous. In contrast to the univariate models such as ARIMA, which analyze on variable in isolation, the VAR model allows multiple variables to be analyze jointly over time.
In recent decades, the VAR model has been widely applied in environmental and climate
studies to explore the interdependence among variables such as temperature, rainfall, soil moisture and atmospheric pressure (Sivajothi & Karthikeyan,2019; Musa & Maijamaa, 2024; Feng et al., 2019). The VAR framework is ideal in such contexts, as it captures the lagged causal interactions between variables without requiring pre-imposed theoretical restrictions. For example, Farrok & Kannan (2016) Used the VAR model to examine the relationship between the yeild of two major major rice crops and three climate variables.
These studies demonstrate the robustness of VAR in handling complex environmental
systems where feedback mechanisms and delays are typical. The VAR model will be estimated using monthly time series data on rainfall and wet days. Each variable will be regressed on its own past values and the past values of the other variable. The appropriate lag length will be selected using standard information criteria such as the Akaike Information Criterion (AIC), Hannah Quin Information Criterion (HQIC) and the Schwarz Bayesian Information Criterion (BIC). Stationarity will be assessed using the Augmented Dickey-Fuller (ADF) test and where necessary, differencing will be applied. If the two series are found to be cointegrated, a Vector Error Correction Model (VECM) will be considered. Diagnostic checks including tests for residual autocorrelation, heteroskedasticity, and normality will be carried out to ensure the model’s validity. Post-estimation analysis will include impulse response functions and forecast error variance decomposition to interpret the dynamic interaction between the two variables.
In summary, the Vector Autoregression model offers a theoretically flexible and empirically grounded approach to understanding the dynamic relationship between rainfall and atmospheric wet days. By accommodating bidirectional influences and lagged interactions, the VAR model not only provides better forecasts but also deeper insights into how climatic variables respond to internal shocks and external changes. Its application in this study is expected to yield valuable findings relevant to climate variability, seasonal prediction, and environmental management.
## 3.4 Statistical Analysis
### 3.4.1 Model Specification: Vector Autoregression(VAR).
A vector Autoregressive model is a multivariate time series model that captures the
relationship between multiple variables as they change over time. It is a generalization of the autoregressive model (AR) model, allowing the analysis of systems where variables influence each other.Each variable is expressed as a linear function of its own past values and other past values in the system. Statistically, the VAR equations for two variables inthisstudyatanylag(p)aregivenas:


<img width="588" height="315" alt="Image" src="https://github.com/user-attachments/assets/2cbe7ce7-b6fd-4445-885a-ea041dff0e95" />
Where:
<img width="604" height="376" alt="Image" src="https://github.com/user-attachments/assets/6e8c3b8a-bece-4948-88fd-c1c1de9d84df" />


<img width="584" height="380" alt="Image" src="https://github.com/user-attachments/assets/74d29cc2-d989-4ed4-a7dc-c399015436ae" />

# RESULTS AND DISCUSSIONS
## 4.1 Introduction
In this chapter of the study, the analysis of the data is presented and it begins with basic statistical analysis involving graphical tools and basic statistics. The Vector Autoregressive methodology is used to model to analyze the relationship between average rainfall and wetness under changing climatic conditions in a multivariate data.The Augmented Dickey-Fuller (ADF) Testis used to determine whether a time series has a unit, which indicates whether the series is stationary or not.Granger causality test developed by Clive Granger, which is the most widely used in VAR Models to test whether the past values of one variable help to predict another variable.Impulse Response Functions(IRF’s) which are the fundamental tools in VAR models that are used to show how one standard deviation shock to one variable affects all variable in the system.

## 4.2 Descriptive Statistical Analysis
This section presents summary statistics for the key variables: average rainfall and wetness. It provides insights into the central tendency, variability, and distributional features of the data before advanced modeling is applied.

## 4.3 Summary Statistics for Average Rainfall and Wetness
<img width="604" height="266" alt="Image" src="https://github.com/user-attachments/assets/5cc1ad57-3fef-4472-aa77-db57d04620e5" />

The summary statistics shows a distinct distributional characteristics between average rainfall and wetness measurements. Average rainfall exhibits a wide range from 4.70 to 320.08 units with a mean of 112.42, which closely aligns with the median of 110.50, suggesting a relatively symmetric distribution. Again, wetness shows a more compressed range from 0.400 to 14.400 units with a mean of 6.382 that slightly exceeds the median of 6.300, indicating a mild right skew

## 4.4 Time Series Plot of Rainfall & Wet Days
<img width="602" height="322" alt="Image" src="https://github.com/user-attachments/assets/5c083c63-1612-4c36-8f0f-fe59c85f68cf" />

The Time series plot displays the two variables (Average Rainfall and Wet days) in the Central Region Ghana, over the period 2019-2024, showing dramatically different scales and patterns. The top graph shows Average Rainfall which exhibits extreme volatility with values ranging from approximately 25 to over 300, displaying sharp spikes and dramatic fluctuations throughout the entire period, with particularly notable peaks in early 2020 and several others. Again, the bottom gragh shows Wet days which remains relatively stable and close to zero throughout the entire time frame, fluctuating only slightly between approximately 0 and 15. This contrast behavior suggests these variables may represent fundamentally different in a different phenomenon- with Average Rainfall showing high sensitivity to external shocks, while ”Wet days demonstrates much more stable, weather related characteristics that vary within a narrow, predictable range.

## 4.5 Stationarity Test
<img width="586" height="223" alt="Image" src="https://github.com/user-attachments/assets/6e2a0a72-0d4f-4093-ad32-d3d0521296a2" />

## 4.6 Optimal Lag Length Selection
Selecting the appropriate lag length is crucial for building a robust VAR model. This
section present svarious information riteria (AIC,SC,HQ,FPE) usedtodeterminethe
optimal lagorder for the multivariate model
<img width="604" height="371" alt="Image" src="https://github.com/user-attachments/assets/9e8fbaa4-2551-408e-b1a7-92b626ac7f10" />

It is likely that,when a VAR includes many lags of variables, it will be difficult to see which sets of variables have significant effects on each dependent variable and which one do not.

## 4.7 Model Estimation and Diagnostics

<img width="604" height="387" alt="Image" src="https://github.com/user-attachments/assets/8c822d1e-1dee-4bf4-b4ba-05a318c1d104" />

## 4.8 Normality Test
<img width="604" height="326" alt="Image" src="https://github.com/user-attachments/assets/806481aa-2822-4ecc-8c42-77811bac29ca" />

## 4.9 Distribution and Normality Checks

<img width="604" height="378" alt="Image" src="https://github.com/user-attachments/assets/4db08c87-7416-42f3-ac17-0f2c1fdcd9d7" />

The figure presents histograms and Q-Q plots for rainfall and surface wetness to assess their distribution and normality. The histograms show the frequency distribution of both variables, with overlaid normal curves for comparison. Rainfall appears slightly skewed, with most observations concentrated around the center and some extreme values indicating possible outliers. Wetness, on the other hand, displays a distribution that is closer to normal, although minor skewness is still evident. Overall, both variables exhibit some deviation from perfect symmetry, suggesting that they are not strictly normally distributed.

The Q-Q plots further evaluate normality by comparing the sample quantiles to theoretical normal quantiles. For rainfall, the points align with the diagonal line in the middle range but deviate at the tails, indicating departures from normality and the presence of outliers. Wetness shows a better fit to the normal line, with most points closely following the diagonal, though slight deviations remain at the extremes. These results suggest that while both variables approximate normality, wetness conforms more closely than rainfall, which may have implications for model assumptions and further data transformation in the VAR analysis.

## 4.10 Granger Causality Test

##### Granger Causality Test for Avg. Rainfall to Wetness
 Null Hypothesis (H0): Average Rainfall does not Granger-cause Wetness.
 Alternative Hypothesis (H1): Average Rainfall does Granger-cause Wetness

 ##### Granger Causality Test for Wetness to Avg. Rainfall
Null Hypothesis (H0): Wetness does not Granger-cause Average Rainfall.
Alternative Hypothesis (H1): Wetness does Granger-cause Average Rainfall.

 <img width="604" height="321" alt="Image" src="https://github.com/user-attachments/assets/4d37fa26-fcd2-4888-91d7-f07cb7c7ec97" />

 Given F-statistics(1.4253) and P-value(0.2442) which is greater than alpha value of (0.05),
we fail to reject the null hypothesis. Therefore, conclude that there is an insufficient evidence that Average Rainfall Granger-causes Wetness Wetness at 5% significant level.
Since the F-statistics (2.151) and P-value of (0.1205) which is greater than alpha value of (0.05), we fail to reject the null hypothesis. Therefore, conclude that there is an insufficient evidence that Wetness Granger-causes Wetness at the 5% significance level.

## 4.11 Response of wet days to a shock in Avg.Rainfal

<img width="604" height="423" alt="Image" src="https://github.com/user-attachments/assets/91d5e98b-548b-46d2-8f13-39b095ae1b7a" />

The graph shows the impulse response function (IRF) illustrates how Average Rainfall
dynamically reacts to an unexpected, one-standard-deviation shock in wet days. The
solid black line represents the estimated response, while the red dashed lines indicate the 95% bootstrap (resampling technique) used to construct confidence intervals. A one unit increase in wetness produces a rapid and substantial rise in rainfall, peaking in the second period at over 15 mm, with an upper bound exceeding 25 mm. This indicates a strong short-term reinforcing feedback between wetness and rainfall, possibly driven by enhanced cloud formation and precipitation processes. The effect declines sharply thereafter, becoming negative between the fourth and fifth periods, which could be due to atmospheric adjustment or moisture depletion.

## 4.12 Response of Avg.Rainfall to a shock in Wet days

<img width="604" height="290" alt="Image" src="https://github.com/user-attachments/assets/3ca1c6ca-2c7f-4a47-a598-e123cf13fe54" />

This graph also illustrate the impulse response function shows how wet days (Wetness) respond to a one-unit shock in average rainfall (Rainfall). The persistent and statistically significant positive relationship between Average Rainfall shocks and Wet days. A positive shock in rainfall leads to an immediate and significant rise in wetness, peaking at approximately 3 units in the first period. This is consistent with the physical expectation that increased rainfall translates into higher atmospheric wetness almost instantaneously.
However, the effect diminishes rapidly, crossing zero around the third period and turning slightly negative in the fourth period. This negative phase may reflect evaporation or short-term balancing effects in the atmosphere. Subsequently, wetness returns toward equilibrium, with fluctuations around zero that are statistically insignificant beyond the sixth period, as the confidence bands encompass the baseline.

## 4.13 Forcast For The Next 6-Months of Rainfall 

<img width="604" height="311" alt="Image" src="https://github.com/user-attachments/assets/0639ceb5-84f7-426a-a9ed-f6771b4638fa" />



## 4.14 Forcast For The Next 6-Months of Wet Days

<img width="604" height="301" alt="Image" src="https://github.com/user-attachments/assets/0cc1905f-5535-4a6d-9ed9-fa3f9e606bea" />

For both series, the solid black line represents historical data, while the dashed blue line after the vertical grey line indicates the forecasted values. The red dotted lines above and below the blue dashed line represent the prediction intervals, showing the range within which future values are expected to fall. In the Average Rainfall series, the values fluctuate significantly, generally staying between-100 and 200, with the forecast showing a continued fluctuating trend but with a wider prediction interval. Similarly, the Wet days series also shows fluctuations, primarily between-5 and 15, and its forecast also continues this fluctuating pattern with a corresponding prediction interval.

# 5 Findings, Conclusion & Recommendations
## 5.1  Findings 
In conclusion, The dramatic divergence in the Average Rainfall and wet days in the Central Region Ghana, in these forecasts after period 6 months , with scenarios ranging from modest decline to severe deterioration, gives recommendations and demands immediate implementation of comprehensive risk management strategies. Decision-makers should establish early warning monitoring systems and intervention triggers well before the critical period 6 months threshold, while simultaneously developing robust contingency plans for both moderate and catastrophic decline scenarios. Given the wide uncertainty intervals suggesting high forecast volatility, organizations must prioritize building resilience through diversification, resource allocation for emergency responses, and proactive mitigation measures during the currently stable period. The steep potential decline trajectories (particularly the red scenario showing values dropping to negative territory) necessitate
urgent stakeholder communication about risks, increased monitoring frequency, and the
development of multiple response protocols that can be activated based on real-time
performance indicators as the forecast period un-folds.

## 5.2 Conclusions
i. The VAR model successfully captured the relationship between rainfall and wet
days.
ii. Granger causality tests showed no directional predictive power between the two
variables.
iii. Impulse Response Functions revealed that rainfall shocks had short-term positive
effects on wet days, while wet-day shocks had weak effects on rainfall.
## 5.3 Recommendations
a. Use findings to support agricultural planning, water resource management, and
disaster preparedness.
b. Future studies should consider integrating other climatic variables (e.g.,
temperature, humidity, wind speed) to enhance model robustness.
c. Regular model updates with new data are recommended to maintain forecast
accuracy under changing climate conditions.

# R Code
library(readxl)

CRDProjectwork <- read_excel("CRDProjectwork.xlsx")

View(CRDProjectwork)

######################## paCKAGES REQUIRED

library(vars)### For estimating var models

library(tseries)### Time series

library(tidyverse)### Collecting of packages

library(stargazer)### For creating tables 

library(ggplot2)

library(forecast)

library(imputeTS)### Handling Missing Values

CRDprojectworkts<- na.interpolation(CRDProjectwork)

CRDprojectworkts

plot(CRDprojectworkts)

############## Converting the data into Time Series Data

Averagets<- ts(CRDProjectwork$rainfall,start = c(2019,1),frequency = 12)

Wetdaysts<- ts(CRDProjectwork$wetness,start = c(2019,1),frequency = 12)

#### checking for individaul Unit Root text

Averagets

Wetdaysts

autoplot(Averagets)

autoplot(Wetdaysts)

acf(Averagets)

pacf(Averagets)

acf(Wetdaysts)

pacf(Wetdaysts)

adfaverage<- adf.test(Averagets)

adfaverage

adfwetdays<-adf.test(Wetdaysts)

adfwetdays

ppaverage<-pp.test(Averagets)

ppaverage

ppwetdays<- pp.test(Wetdaysts)

ppwetdays

kpss.test(Averagets)

kpss.test(Wetdaysts)

############# Putting together the dataset

combinets<- cbind(Averagets,Wetdaysts)

combinets

summary(combinets)

ndiffs(combinets)

autoplot(combinets,main= "Average Rainfall and Wetness",xlab = "VAR plot",ylab ="Time" )

firstdiff<-diff(combinets)

firstdiff

seconddiff<-diff(firstdiff)

seconddiff

autoplot(firstdiff)

autoplot(seconddiff)

ndiffs(combinets)

Acf(combinets,col='maroon', main = 'figure 1.1')


Pacf(combinets,col='maroon',main = 'figure 1.2')

#### Optimal lag lenght

laglenght<-VARselect(combinets,lag.max = 10)

laglenght

##### Checking for residuals

residualsts<-(laglenght)

laglenght

#### Estimation of VAR

estimts<- VAR(combinets,p=6,type = 'none')

estimts

summary(estimts)


#### stargazer

stargazer(estimts[["varresults"]],type = 'text')

######## Check for stable model

roots(estimts,modulus = TRUE)


##### Granger causality test

grangerAveragets <-causality(estimts,cause = "Averagets")

grangerAveragets

grangerAveragets$Granger

grangerWetdays <-causality(estimts,cause = "Wetdaysts")

grangerWetdays

grangerWetdays$Granger

#### IRFs; 

#### Wetdaysts response to Averagets shock

irf1<-irf(estimts,impulse = "Averagets",response = "Wetdaysts",n.ahead = 50, boot = TRUE,runs = 300,ci=0.95)

irf1

plot(irf1,xlab="Wetdaysts",main="Wetdaysts response to Averagets shock")


#### Averagets response to Wetdaysts shock

irf2<-irf(estimts,impulse = "Wetdaysts",response = "Averagets",n.ahead = 50, boot = TRUE,runs = 300,ci=0.95)

irf2

plot(irf2,xlab="Averagets",main="Averagets response to Wetdaysts shock")


#### VAriance Decompositions

vdts<- fevd(estimts,n.ahead = 50)

plot(vdts)

forecastts<- predict(estimts,n.ahead = 12,ci=95)

forecastts

plot(forecastts)



# Group Members
KOMMAAK BISMARK GORIB

MICAH ELSIE

PEPRAH POKUAA GIFTY

BAFFOUR AWUAH JUSTICE


# References 
Reference
L¨utkepohl, H., 2005. New Introduction to Multiple Time Series
Analysis. Berlin: Springer.
https://doi.org/10.1007/978-3-540-27752-1

Tesfaye, K. and Walker, S., 2004. Matching of crop and environment
for optimal water use: the case of Ethiopia. Physics and Chemistry of
the Earth, Parts a/b/c, 29(15-18), pp.1061-1067.
https://doi.org/10.1016/j.pce.2004.09.024

Sims, C.A., 1980. Macroeconomics and reality. Econometrica, 48(1),
pp.1-48.
https://doi.org/10.2307/1912017
