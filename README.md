

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/michaelMatve/API_Attack_Mitigation">
    <img src="images/api_logo_trans_back.png" alt="Logo" width="100" height="100">
  </a>

  <h3 align="center">API_Attack_Mitigation</h3>

  <p align="center">
    A python library that detect and block malicious API request.
    <br />
 </p>
</div>




<!-- ABOUT THE PROJECT -->
## About The Project

With the increasing prevalence of API servers, the number of attacks targeting them has also grown. This highlights the necessity for an API Attack Mitigation system that safeguards both the server and its users. To address this need, we conducted thorough research and developed an easy-to-use protection system that offers effective defense.

Here's why:
* you want to protect your server
* you want to protect the user and his information
* you want to protect your company
* easy-to-use and fixable.

Our project focuses on creating a Python package for an API Attack Mitigation layer. This package enables developers to easily add a security layer to their API servers, effectively protecting them against malicious attacks. 


We analyzed API attacks and existing solutions, finding that most focus on low-level detection like firewalls. While effective, these solutions are complex and inflexible. To address this, we developed a Python library leveraging ModSecurity's rules database. Our high-level approach offers greater flexibility and user-friendliness.
Our Python library supports Flask and FastAPI servers and can be adapted for other API interfaces using the adapter design pattern. By capitalizing on the utilization of an actively maintained ModSecurity rules database as the primary defensive measure, complemented by an AI model serving as the secondary safeguard, our library consistently maintains its currency in order to achieve optimal effectiveness in accurately categorizing incoming requests, irrespective of whether they entail familiar or unfamiliar attack vectors.
With its capability to detect and block a wide range of API attacks such as SQL injection, RCE, directory traversal, XSS, and more, our library provides comprehensive protection. To offer users detailed diagnosis, we generate a log file that tracks every request.
<p align="right">(<a href="#readme-top">back to top</a>)</p>


### Log File Example:


  <a href="https://github.com/michaelMatve/API_Attack_Mitigation">
    <img src="images/log_example.png" alt="log_code" width="800" height="400">
  </a>
<p align="right">(<a href="#readme-top">back to top</a>)</p>



### Built With

<a href="https://www.python.org/">
  <img src="https://www.python.org/static/img/python-logo.png" alt="Python" height="24">
</a>

### Core Rule Set

The Core Rule Set is a set of security rules designed to provide protection

<a href="https://coreruleset.org/installation/">
  <img src="https://raw.githubusercontent.com/michaelMatve/API_Attack_Mitigation/main/images/mod_logo.png" alt="Core Rule Set" height="50">
</a>

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

This section provides an example of how to install and utilize our library.

### Installation
To install the API_Attack_Mitigation library:</br>
first you need to install git-lfs. Run the following command:
   ```sh
   sudo apt-get install git-lfs
   ```

then you can use pip. Run the following command:
   ```sh
   pip install git+https://github.com/ArielCyber/API_SECURITY_LIBRARY.git@v0.0.6
   ```
## Usage

Here, you can see how to use this library for API request attack mitigation on the server.

1. Import the necessary module in your Python code:
```sh
   from API_Attack_Mitigation_Package import API_Detector
```
2. Create an instance of the API_Detector class:
```sh
   api_detector = API_Detector.API_Detector()
```
Furthermore, the API_Detector.API_Detector() function accepts additional arguments that offer customization options:

AI_flag: This argument determines whether the AI layer should be utilized or not. It accepts either False or True. By default, it is set to True.

threshold: Specify the threshold value for the AI layer. The default value is 95.

min_points: Set the minimum number of points required for training. When the default value is 16, it is advised to provide 16 or more points.

number_of_compare_points: Indicate the number of comparison points utilized by the AI layer. The default value is 1000.

save_every_K_point: Define the frequency at which the new model should be saved. The default is every 100 points.

model_file_path: Provide the path to the AI layer model that has been constructed. The default path is "api_models/knn_model.bin".

ids_file_path: Supply the path to the file containing the AI layer IDs that have been generated. The default path is "api_models/points_ids.json".

ai_paranoia_level: Determine the paranoia level of the AI layer. It can be either 0 or 1. When set to 0, the AI layer doesn't inspect unknown header when the default is 0.

rule_paranoia_level: Set the rule paranoia level, which can range from 0 to 4. The default value is 1.
3. Detect a potentially malicious request using the detect_malicious_request method:
```sh
   result = asyncio.run(api_detector.detect_malicious_request(request, "flask"))
```
The detect_malicious_request method takes two parameters: the request object representing the incoming API request and the framework name ("flask" in this example). The method returns False if the request is benign and True if it is identified as a potential malware or attack.
<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Server Code Example:


  <a href="https://github.com/michaelMatve/API_Attack_Mitigation">
    <img src="images/code_example.png" alt="server_code" width="600" height="400">
  </a>
<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the ariel university License.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Michael Matveev - [@add_soon]() - michael.matve@gmail.com

Eylon Naamat - [@add_soon]() - eylonnaamat@gmail.com

Project Link: [https://github.com/michaelMatve/API_Attack_Mitigation](https://github.com/michaelMatve/API_Attack_Mitigation)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

* [coreruleset](https://coreruleset.org/installation/)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Guides for the project

* Prof. Amit Dvir
* Dr. Ran Dubin
* Mr. Udi Aharon
<p align="right">(<a href="#readme-top">back to top</a>)</p>

