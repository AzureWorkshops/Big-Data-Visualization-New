## Exercise 2: Check the weather

**Duration:** 20 mins

**Synopsis:** In this exercise, attendees will integrate the 10-day weather forecast into the sample solution.

### **Task 1:** Register for trial account in WeatherUnderground.com

1.	To retrieve the 10-day hourly weather forecast, you will use an API from [WeatherUnderground.com](https://www.wunderground.com/). There is a free developer version that provides you access to the API you need for this workshop.

2.	Navigate to [http://www.wunderground.com/weather/api/](http://www.wunderground.com/weather/api/).

3.	Click **Explore My Options**.
<img src="../images/explore_my_options.jpg" class="block"/>

4.	On the Get Your API Key page, select **Anvil Plan**.
<img src="../images/anvil_plan.jpg" class="block"/>

5.	Scroll down until you see the area titled How much will you use our service? Ensure Developer is selected.
<img src="../images/weather_service_use.jpg" class="block"/>

6.	Click **Purchase Key**.
<img src="../images/purchase_key.jpg" class="block"/>

7.	Complete the Create an Account form by providing your email, username and a password and agreeing to the terms. Click Basic – Free.
<img src="../images/create_an_account.jpg" class="block"/>

8.	Back on the Get Your API Key page, re-select Anvil and click Purchase Key.

9.	In a few moments you should receive a confirmation email at the email address you provided. Click the link found within the email.
<img src="../images/confirmation_email.jpg" class="block"/>

10.	On the page that loads, you will see a message like the following:
<img src="../images/successful_validation.jpg" class="block"/>

11.	Complete the brief contact form. When answering where will the API be used, select **Website**. For Will the API be used for commercial use, select **No**. Click **Purchase Key**.
<img src="../images/contact_form.jpg" class="block"/>

12.	You should be taken to a page that displays your key, similar to the following:
<img src="../images/key_display.jpg" class="block"/>

13.	Take note of your API Key. It is available from the text box labeled **Key ID**.

14.	To verify that your API Key is working, modify the following URL to include your API Key: [http://api.wunderground.com/api/\<YOURAPIKEY\>/hourly10day/q/CA/SEATAC.json](http://api.wunderground.com/api/<YOURAPIKEY>/hourly10day/q/CA/SEATAC.json).

15.	Open your modified link in a browser, you should get a JSON result showing the 10-day, hourly weather forecast for the Seattle-Tacoma International Airport.
<img src="../images/json_results.jpg" class="block"/>

### **Task 2:** Update sample Web App with API Key

1.	Next, you will update the sample app with your Weather Underground API Key. 

2.	With the sample app open in Visual Studio, in Solution Explorer, right-click the project and select **Properties**.

3.	Click the **Settings** tab.
<img src="../images/settings_tab.jpg" class="block"/>

4.	Edit the value for the Weather_APIKey and click **Save**.

5.	In Visual Studio Solution Explorer, right-click your project, select **Publish**, and then click **Publish**.

6.	On your deployed web app, change the date of the flight to tomorrow's date (or another future date no further than 10 days away). 

7. Change the **From** airport to **ATL**, then click **Predict Delay**

<img src="../images/predict_delay_change_from_airport.jpg" class="block"/>

8. You should see the weather icon display on the right. If you hover over the icon, you will get the description of the weather conditions forecasted. At this point, Delay Prediction should display not configured. You will set Delay Prediction up shortly.
<img src="../images/predict_delay.jpg" class="block"/>