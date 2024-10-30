# Splunk-Cloud-Platform-Wndows-Forwarder
<h2>Description</h2>
In this project we will forward data into the Splunk Cloud Platform
<br />
<br/>  Splunk Forwarder architecture: <br/>
<img src="https://github.com/user-attachments/assets/f610827a-cdca-479c-9c63-271935de836a"/>


<h2>Languages and Utilities Used</h2>

Splunk Cloud Platform, Windows 10 Virtual Machine

<h2>Environments Used </h2>

- <b>Windows 10, Splunk portal </b>

<h2>Project walk-through:</h2>
<br/>
<p align="center">

 

### **Prerequisites**  
- Sign up for [Splunk Cloud Free Trial](https://www.splunk.com/).
- Have a Windows Virtual Machine 

##  Step 1: Download the Universal Forwarder (UF) credentials 
<br/> Navigate to the Splunk Cloud platform and click on the Universal Forwarder on the left to download the UF credentials package <br/>
<img src="https://github.com/user-attachments/assets/534317f0-68fa-47a0-a0e6-361cbd61c8a8"/>


## Step 2: Copy the .spl (UF credentials package) to the Windows Machine
<br/> Navigate to the Splunk Cloud Platform on the Windows Virtual Machine and go to "free trials and downloads" to find the Universal Forwarder <br/>
<img src="https://github.com/user-attachments/assets/36fcf3e5-9b4d-4948-bd42-c522429429ed"/>
<img src="https://github.com/user-attachments/assets/117728f2-4705-43e3-ae9d-a82e1bd239a4"/>

## Once installed follow the prompts:

<img src="https://github.com/user-attachments/assets/02d21b7d-dc0e-4ad3-87a3-e70c05c1148c"/>
<img src="https://github.com/user-attachments/assets/8a9cf2d8-509b-45ac-88ed-d6e7fb03599b"/>
<img src="https://github.com/user-attachments/assets/74366f91-aef9-4c02-9f53-bed40edb916e"/>

<br/> Check off all the boxes to gather as much data as possible: <br/>

<img src="https://github.com/user-attachments/assets/0a9216ab-9b10-4eda-99e0-28b1ae371ee2"/>

<br/> Enter a username and uncheck the generate random password box: <br/>
<img src="https://github.com/user-attachments/assets/5b757f9d-f1a9-4133-acae-5c3d6dc9f074"/>

<br/> We don't have a deployment server so click next <br/>
<img src="https://github.com/user-attachments/assets/e3763114-1fe7-43c4-ae3c-5140072eff59"/>

<br/> Finally click install then finish once completed <br/>
<img src="https://github.com/user-attachments/assets/42c46e62-4154-4c09-b524-6088431592ea"/>

## Open the command prompt as administrator 
<br/> Enter the Splunk Universal Forwarder <br/>

```Bash
cd \
cd Program Files
cd SplunkUniversalForwarder
cd bin
```

<img src="https://github.com/user-attachments/assets/f96ec9b7-f5c5-4f56-af01-8348083b8c3f"/>

## 
<br/> Run the splunk executable to the .spl file path that we downloaded then enter credentials created earlier <br/>

```Bash
splunk.exe install app C:\Users\Devin\Downloads 
```

<img src="https://github.com/user-attachments/assets/b9926d42-b40e-4f30-aca5-40810407dae2"/>

<br/> Now restart the splunk forwarder <br/>

```Bash
splunk.exe restart
```

<img src="https://github.com/user-attachments/assets/73c81ee9-64ef-470c-b9ef-1cba52ae8454"/>

## Now navigate back to the Splunk Cloud Platform to verify that data is coming in
<br/> Go to "search and reporting" run the following to see how much data each forwarder is sending to the indexer <br/>

```Bash
index="_internal" sourcetype="splunkd" component="Metrics" group="per_host_thruput"
```

<img src="https://github.com/user-attachments/assets/edb2eca5-6885-4a9f-9237-b1731f1d4a1b"/>

## This data can then be saved and visualized into a dashboard:

<img src="https://github.com/user-attachments/assets/e7478745-8ea8-41ec-997e-fe171e1a34a0"/>
<img src="https://github.com/user-attachments/assets/0e6fb6c6-443e-4073-97bb-27e0b1a1bf03"/>
