# Codistan: It is a code compiler for cpp

## Requirement:
#### python3.7, Django, django-rest-framework, knox, pillow



# Api:

### Register: http://localhost:8000/ide/register/

  > Send a post request with JSON Data 
    {
      "username": "wasim",
      "email": "wasim@gmail.com",
      "password": "Root@wasim"
    }
    
### Login: http://localhost:8000/ide/login/  

  > Send a get request with Joson Data <br/>
    {
      "username": "wasim",
      "password": "Root@wasim"
    } <br/>
  > You will get a token. After Succesfully getting loged in.
  
### Submitting your Code: http://localhost:8000/ide/submit/
 
 #### Json only accept String data so while sending code we need to convert it into a single line string

  > Send a post request With headers and JSON <br/>
    Header: {"Authorization" : "Token c883f8d98be6523118837d4318ec7629afc2b0cabaf9ac904d69b6bf701b6149" } <br/>
    JSON: { <br/>
            "code" : "#include <iostream>\nusing namespace std;int main(){std::cout<<(5*34)<<endl; return 0;}", <br/>
            "language": "cpp" <br/>
          } <br/>

### Getting result of your Code: http://localhost:8000/ide/submit/

  > Send a get request With headers <br/>
    Header: {"Authorization" : "Token c883f8d98be6523118837d4318ec7629afc2b0cabaf9ac904d69b6bf701b6149" }
