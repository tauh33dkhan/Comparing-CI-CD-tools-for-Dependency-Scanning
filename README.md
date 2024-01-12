# Comparing-CI-CD-tools-for-Dependency-Scanning
| Points                  | Snyk                                           | Vet                                                   | owasp-dep                                                    | gemnassium                                                  |
|-------------------------|-------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------------|-------------------------------------------------------------|
| NodeJS                  | Works only using package.json                  | Does not work without package-lock.json                 | Does not work, we need package-lock.json                       |                                                               |
| Java                    | Works with pom.xml file                         | Works with pom.xml                                      | Did not work when provided pom.xml file                        |                                                               |
| Auto merge requests     | Yes, creates merge request if vulnerability found | Not able to use it with CI/CD                           | Not able to use it with CI/CD                                |                                                               |
| Suggests fix            | Suggests the version in which vulnerability is fixed | Suggests the latest version                             | Suggests the version in which vulnerability is fixed         |                                                               |
| Ease of use             | Easy to track vulnerability from Snyk dashboard | Not so easy, depends on CI/CD configuration             | Not so easy, depends on CI/CD configuration                  |                                                               |
| Report format           | Very good                                       | Not able to use it with CI/CD                           | Not able to use it with CI/CD                                |                                                               |
| Hosting                 | Snyk                                            | We can download the binary, create a Docker container, push it to the organization GitLab container repository, then use the Docker image to run the scan | Same method can be used here. We can also use the Dependency Check image hosted by OWASP or clone it on our GitHub org |                                                               |
| Problem Facing When Configuring with CI/CD | No problem                                    | Created Docker image, but when I run the scan from Docker, I get zero vulnerabilities and it is not clear why it is not able to detect vulnerabilities. I think it is an SSL-related issue; will check this | After doing multiple tweaks, I am able to run the scan, but the output is not showing. Need to figure out how to use the output and if it is possible to create the MR request | After doing multiple tweaks, I am able to run the scan, but the output is not showing. Need to figure out how to use the output and if it is possible to create the MR request |

## Snyk Dashboard

* It shows the package magnger files detected in a particular repository and also shows the vulnerabilities found:

![image](https://github.com/tauh33dkhan/Comparing-CI-CD-tools-for-Dependency-Scanning/assets/43419559/c4a9902a-d702-4815-92b4-3f4a7cb622e0)

## Vulnerability fixing details

* Once you select the package manager in which you want to fix vulnerabilties it will open the detail page and also proivdes option to create the merge request to fix vulnerabilities there are other option also available such as who is the owner of the project etc.
![image](https://github.com/tauh33dkhan/Comparing-CI-CD-tools-for-Dependency-Scanning/assets/43419559/10271127-6dbe-4b75-9359-799badb82b3d)

* Additional features:
![image](https://github.com/tauh33dkhan/Comparing-CI-CD-tools-for-Dependency-Scanning/assets/43419559/810f74b8-4f6d-4523-8280-0164152202c3)

![image](https://github.com/tauh33dkhan/Comparing-CI-CD-tools-for-Dependency-Scanning/assets/43419559/13d6991a-9e46-4a48-9a29-e0b131d0c48f)


### OPEN SOURCE DEPENDENCY CHECK HTML Report

https://github.com/tauh33dkhan/Comparing-CI-CD-tools-for-Dependency-Scanning/blob/main/dependency-check-report.html

![image](https://github.com/tauh33dkhan/Comparing-CI-CD-tools-for-Dependency-Scanning/assets/43419559/8e831193-597d-4fd7-b4f0-221dd0e5c0eb)

### VET cli report

![image](https://github.com/tauh33dkhan/Comparing-CI-CD-tools-for-Dependency-Scanning/assets/43419559/dbc531c7-36b8-4287-9f72-cd45c3308195)


OWASP Dependency check, VET and gemnasium can be used open MR but due to lack of complete documentation it is causing problem.



