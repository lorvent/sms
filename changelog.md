#ChangeLog

### 29-10-2015
 * changes in teacher api methods

### 29-10-2015
 * changes in general api methods
 * some changes in teacher api and add edit_attendance

### 28-10-2015
 * add attendances_date to teacher api to get attendances for selected date
 * small change notices in to teacher api
 * add edit_notice into teacher api & some methods in general has changes
  
### 23-10-2015
 * fix params of applying_leave method in teacher
 
### 23-10-2015
 * fix name of methods: dairy->diary
 * add subjects to teacher api to get subjects for selected group
 * add hours to teacher api to get list of hours for selected group,subject and date
 * add edit_diary to teacher api for edit diary record
 
### 23-10-2015
 * add dairy_date to teacher api

### 22-10-2015
 * add school_year_student into teacher api for get school year and first selected group for teacher
 * add school_year_child into parent api to get last school year and last child which added
 * add school_year_student into student api to get last school year and student_id for student user

### 21-10-2015
 * add fee_details into parent api fo get student fee details

### 19-10-2015
 * add exam_group method for get all exam for selected group

### 17-10-2015
 * add applying_leave method for get all applying leave for teacher and parent and post_applying_leave & delete_applying_leave port post and delete applying leave for student by parent

### 16-10-2015
 * add exam_marks method for get all exams for teacher,student and parent and exam_marks_details for get details of selected exam

### 15-10-2015
 * add dairy_date method for get students and parents to get dairy for selected date and student

### 14-10-2015
 * add student_subject method for get students subject list with teacher which is added to teach that subject

### 13-10-2015
 * add user_list method in librarian to get list of users for issuing the book
 
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