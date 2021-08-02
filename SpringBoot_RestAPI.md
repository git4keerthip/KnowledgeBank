# SpringBoot_RestAPI
- Spring Dev tools can be excluded in production by adding exludeDevTools true in pom.xmls
## Spring Data JPA 
- This has 3 repository  interfaces in this. CURD repository, JPA repository, PagingAndSorting repository

## ResponseStatus Exceptions

- Spring 3 has @ResponseStatus annotation which had to be called on custom exception class, so for all types of that exception class same response code has to be written.This is tighlty coupled to exception class.
```
    @ResponseStatus(code = HTTPSTATUS.Not_Found , reason = " user not found ")
    public ExceptionClass extends Exception(){
    ....
    }
```
- Spring 5 introduced Responsestatus exception class which is a runtime exception, so no explicit check is needed.
  - We can directly throw this response status exception with status code we want, no need of creating custom exception classes.
  - Downside of this is code duplication in multiple controllers, but using @ControllerAdvice would solve this.

## @ControllerAdvice

- Centralized points for exceptions. Intercepts exceptions thrown by multiple controllers and respond with error message instead of requestmapping methods handling.
- Recommended to have one controller advice per application
- @RestcontrollerAdvisor is combination of @ControllerAdvice and @ResponseBody
```
- @ControllerAdvice
public class GlobalExceptionHandler {
   
    @ExceptionHandler({ UserNotFoundException.class, ContentNotAllowedException.class })
    public final ResponseEntity<ApiError> handleException(Exception ex, WebRequest request) {
        HttpHeaders headers = new HttpHeaders();

        if (ex instanceof UserNotFoundException) {
        ....
        return handleErrorsDowntheLine();
    
        }
```
## HTTP Status codes series 
HTTP Status code is also enum
```
public static enum Series {
        INFORMATIONAL(1),
        SUCCESSFUL(2),
        REDIRECTION(3),
        CLIENT_ERROR(4),
        SERVER_ERROR(5);
```
## Spring HATEOAS
HypherMedia As The Engine of Application status
- HATEOAS is the constraint of REST Application architecture, it gives followup links in response so that client knows which endpoint to hit without going to API documentation. 

## Data Transfer Objects DTO
DTO are objects that carry data between processes.

