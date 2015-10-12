#ChangeLog

### 12-10-2015
 * add subject_list method in librarian to get list of subjects with direction and class

### 09-10-2015
 * add method transportations_directions which return all transportation with directions 
 * fix in invoices in parent api-change param
 * fix some api parent methods
 
### 08-10-2015
 * add date into returned marks 
 * add list of exams for selected subject for student and parent user
 
### 06-10-2015
 * add subject books for selected subject
 
### 02-10-2015
 * add in marks and attendances school year
 * add method to teacher justify_attendance
 * fixes in reserved books and add reserved books for selected user
 * add borrowed books for user

### 01-10-2015
 * divided school year selects on roles

### 09-09-2015
 * add method for edit book for librarian
 * change name of method for add new book for librarian
 
### 09-09-2015
 * add more fields to books to create and return values of search the books
 
### 07-09-2015
 * login endpoint now returns token, user object and role, no need to call other apis
 * README.md updated to reflect above point