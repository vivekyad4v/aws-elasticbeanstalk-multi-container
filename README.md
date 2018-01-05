[![](http://www.iconninja.com/files/646/741/224/original-linkedin-color-icon.png =100x20)](https://www.linkedin.com/in/vivekyad4v)

## AWS-ElasticBeantsalk-MultiContainer

Dockerrun version:'2', deploy docker images to ECS using ElasticBeanstalk

<a href="https://github.com/vivekyad4v?tab=followers"><img align="right" width="200" height="183" src="https://s3.amazonaws.com/github/ribbons/forkme_left_green_007200.png" /></a>

#### Python API - Dockerrun.aws.json.python.api.tmpl
  - AWS Dockerrun version:2 template
  - Multiple container definitions - volumes, memory, ports, command etc
  - ENV variables for deployment -

        | ACCOUNT_ID  | AWS account ID |
        | ENVIRON     | dev, uat, prod etc |
        | NGINXM      | Nginx server memory in MB |
        | WSGIM       | API(python) server memory in MB |
        | APP_ENV     | ElasticBeanstalk environment name |
        | BUILD_TAG   | Tag name/no. of your deployment |
        | GIT_COMMIT  | Git #commit |

  - Depoyment
  ``` sh
 $ sed -e "s/\${ACCOUNT_ID}/${ACCOUNT_ID}/" -e "s/\${ENVIRON}/${ENVIRON}/" -e "s/\${NGINXM}/${NGINXM}/" -e "s/\${WSGIM}/${WSGIM}/" Dockerrun.aws.python.api.json.tmpl > Dockerrun.aws.json
 
 $ eb deploy $APP_ENV -l ${BUILD_TAG}_${GIT_COMMIT} --timeout 30

  ```
