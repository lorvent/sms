FORMAT: 1A

# API_SMS

# Auth
Authentication related endpoints

## Login to system [POST /login]


+ Request (application/json)
    + Body

            {
                "email": "foo",
                "password": "bar"
            }

+ Response 200 (application/json)
    + Body

            {
                "token": "token",
                "user": {
                    "id": 4,
                    "first_name": "Teacher",
                    "last_name": "Doe",
                    "email": "teacher@sms.com",
                    "last_login": "2015-09-07 19:27:08",
                    "address": "Address",
                    "picture": "image.jpg",
                    "mobile": "+545154515",
                    "phone": "+545154515",
                    "gender": 0,
                    "birth_date": "2015-06-02",
                    "birth_city": "Banja Luka"
                },
                "role": "teacher"
            }

+ Response 401 (application/json)
    + Body

            {
                "error": "invalid_credentials"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "could_not_create_token"
            }

## Refresh token [GET /refresh]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "token": "token"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "could_not_create_token"
            }

# General
General endpoints which can be accessed by any user group

## Behaviors [GET /behaviors]
Get all behaviors
This list use teacher to put behavior to student

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "title": "Good"
                },
                {
                    "id": "2",
                    "title": "Worse"
                }
            ]

## Books [GET /books]
Get all books
This method use all roles to select which book they like to issue

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "subject": "History",
                    "title": "History of world 1",
                    "author": "Group of authors",
                    "year": "2015",
                    "internal": "2015/15",
                    "publisher": "Book publisher",
                    "version": "0.2",
                    "issued": 2,
                    "quantity": 2
                },
                {
                    "id": "2",
                    "subject": "English",
                    "title": "English 2",
                    "author": "Group of authors",
                    "year": "2015",
                    "internal": "2015/15",
                    "publisher": "Book publisher 2",
                    "version": "0.1",
                    "issued": 2,
                    "quantity": 2
                }
            ]

## Directions [GET /directions]
Get all directions
This is list of all directions of school mostly is for admin who create groups of students

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "title": "Sociology",
                    "duration": "3"
                },
                {
                    "id": "2",
                    "title": "History",
                    "duration": "4"
                }
            ]

## Dormitories [GET /dormitories]
Get all dormitories
Method for admin to list all dormitories in school

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "title": "Student hotel 1"
                },
                {
                    "id": "2",
                    "title": "Student hotel 2"
                }
            ]

## Dormitory rooms [GET /dormitory_rooms]
Get all dormitory rooms
Method for admin to list all dormitory rooms in school

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "dormitory": "Student hotel 1",
                    "title": "Room 1"
                },
                {
                    "id": "2",
                    "dormitory": "Student hotel 2",
                    "title": "Room 1"
                }
            ]

## Dormitory beds [GET /dormitory_beds]
Get all dormitory beds
Method for admin to list all dormitory beds and know which student is in which room in school

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "dormitory": "Student hotel 1",
                    "dormitory_room": "Room 1",
                    "bed": "Bed 1"
                },
                {
                    "id": "2",
                    "dormitory": "Student hotel 1",
                    "dormitory_room": "Room 2",
                    "bed": "Bed 2"
                }
            ]

## Mark types [GET /mark_types]
Get all mark types
Teachers need this to choose which is mark type

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "title": "Oral"
                },
                {
                    "id": "2",
                    "title": "Writing"
                }
            ]

## Mark values [GET /mark_values]
Get all mark values
Teachers need this to choose which is mark value

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "title": "A"
                },
                {
                    "id": "2",
                    "title": "B"
                }
            ]

## Notice types [GET /notice_types]
Get all notice types
Teachers need this to choose which is notice type

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "title": "Notice of oral"
                },
                {
                    "id": "2",
                    "title": "Notice of writing test"
                }
            ]

## Notifications [GET /notifications]
Get all notifications
All users get all they notification

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "read": "0",
                    "title": "Notification 1",
                    "content": "This is content of notification",
                    "date": "2015-10-12"
                }
            ]

## Sections [GET /sections]
Get all sections
Admin role to get all sections

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "school_year": "1"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "title": "1 - 1",
                    "section_teacher": "Teacher Name 1"
                },
                {
                    "id": "2",
                    "title": "1 - 2",
                    "section_teacher": "Teacher Name 2"
                }
            ]

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Sections [GET /semesters]
Get all semesters
Admin list of all semesters

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "school_year": "1"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "title": "First semester",
                    "start": "2015-06-12",
                    "end": "2015-12-31"
                }
            ]

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Subjects [GET /subjects]
Get all subjects for selected direction
This used admin for select all subject for selected direction to can add teacher to subject on selected school year

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "direction_id": "1"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "title": "English",
                    "class": "3",
                    "order": "2"
                }
            ]

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Transportations [GET /transportations]
List all transportations used for all roles

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "title": "Go to school",
                    "start": "7:00",
                    "end": "7:30"
                }
            ]

## Transportation directions [GET /transportation_directions]
List all transportation directions for selected transportation used for all roles

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "transportation": "1"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "name": "Direction name"
                }
            ]

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Messages [GET /messages]
Get all messages used for all roles to get user messages

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "received": [
                        {
                            "id": 1,
                            "parent_message_id": null,
                            "read": 0,
                            "title": "This is title",
                            "content": "This is message",
                            "created_at": "2015-11-30 15:30:12"
                        }
                    ],
                    "send": [
                        {
                            "id": 2,
                            "parent_message_id": 1,
                            "read": 0,
                            "title": "This is replay title",
                            "content": "This is replay message",
                            "created_at": "2015-11-30 15:33:05"
                        }
                    ]
                }
            ]

## Send message to user, used for all roles to send user messages [POST /send_message]
Send message to user or replay to message. If send parent_message_id greater then 0 than it's replay to message, if 0 then is new message

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "user_id_receiver": "1",
                "parent_message_id": "1",
                "title": "This is title of message",
                "content": "This is content of message"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Users [GET /users]
Get all users, all role can use it to send message

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "first_name": "First name",
                    "last_name": "Last name"
                }
            ]

## Reserve book [POST /reserve_book]
Reserve book from user, all role can reseve book

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "book_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Payments for user [GET /payments]
Get all payments for user, student select there payment and parent select for there students sending user_id of that student

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "user_id": "1"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": 1,
                    "amount": "10.5",
                    "title": "This is title of payment",
                    "description": "This is description of payment",
                    "created_at": "2015-06-05 10:55:11"
                }
            ]

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get student for user and school year, parent use it for there students [GET /student]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "user_id": "1",
                "school_year_id": "1"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "student_id": "1",
                    "section_id": "1",
                    "section_name": "1-2",
                    "order": "2"
                }
            ]

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get search books [GET /book_search]


+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "search": "Test book"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "subject": "History",
                    "title": "History of world 1",
                    "author": "Group of authors",
                    "year": "2015",
                    "internal": "2015/15",
                    "publisher": "Book publisher",
                    "version": "0.2",
                    "issued": 2,
                    "quantity": 2
                },
                {
                    "id": "2",
                    "subject": "English",
                    "title": "English 2",
                    "author": "Group of authors",
                    "year": "2015",
                    "internal": "2015/15",
                    "publisher": "Book publisher",
                    "version": "0.2",
                    "issued": 1,
                    "quantity": 2
                }
            ]

## Get search users [GET /user_search]


+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "search": "Test user"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "name": "Name Surname"
                }
            ]

## Reserved books for user [GET /reserved_user_books]
Get all reserved books for user

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "user_id": 5
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "title": "Book for mathematics",
                    "author": "Group of authors",
                    "subject": "Mathematics",
                    "reserved": "2015-08-10"
                }
            ]

## Borrowed books for user [GET /borrowed_user_books]
Get all borrowed books for user

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "user_id": 5
            }

+ Response 200 (application/json)
    + Body

            {
                "books": [
                    {
                        "id": 12,
                        "title": "EngLib",
                        "author": "Ruth D. Brown",
                        "subject": "English",
                        "internal": "12-15",
                        "get": "2015-09-11"
                    },
                    {
                        "id": 13,
                        "title": "SciLib",
                        "author": "Matthew D. Stewart",
                        "subject": "Science",
                        "internal": "158/59",
                        "get": "2015-09-11"
                    }
                ],
                "user": {
                    "id": 15,
                    "name": "Full Name",
                    "email": "address@sms.com",
                    "address": "Kincheloe Road Portland",
                    "mobile": "345376587657",
                    "phone": "",
                    "gender": 1
                }
            }

## Books for subject [GET /subject_books]
Get all books for subject

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "subject_id": "5"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": "1",
                    "title": "Book for mathematics",
                    "author": "Group of authors",
                    "year": "2015",
                    "internal": "15-14",
                    "publisher": "Book publisher",
                    "version": "0.2",
                    "quantity": 2,
                    "issued": 1
                }
            ]

## Feedback [GET /feedback]
Get all Feedback for user

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "feedback": {
                    "id": 1,
                    "title": "This is title of notice",
                    "type": "request",
                    "description": "This is description of notice",
                    "date": "2015-02-02 15:32:11"
                }
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post feedback from user [POST /post_feedback]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "feedback_type": "request|praise|contact|error|proposal",
                "role": "student\librarian|teacher|parent",
                "title": "This is title",
                "description": "This is description"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Transportation [GET /transportations_directions]
Get all transportation routes

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "transport": {
                    "id": 1,
                    "title": "This is title of notice",
                    "start": "2015-02-02",
                    "end": "",
                    "locations": {
                        "id": 1,
                        "name": "San Jose",
                        "lat": "",
                        "lang": ""
                    }
                }
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

# Student [/student]
Student endpoints, can be accessed only with role "student"

## School year for student [GET /student/school_years]
Get all school years with current school year name and id and other school years that he/she can select.
This method use all roles because all data(students, sections, marks, behaviors,semesters,attendances) are depend on school year

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": 1,
                "school_year": 1
            }

+ Response 200 (application/json)
    + Body

            {
                "current_school_value": "2014/2015",
                "current_school_id": 1,
                "other_school_years": {
                    "id": 1,
                    "title": "2014/2015"
                }
            }

## Timetable for student [GET /student/timetable]
Get timetable for student with getting his token and role student
This method return array of array: first array has number of hour, first subarray is array for number of day and
in that array have objects that represent subject and teacher that teaches

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "school_year": "1"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "1": {
                        "1": {
                            "id": 10,
                            "subject": "English",
                            "teacher": "Test teacher 1"
                        },
                        "2": {
                            "id": 11,
                            "subject": "Serbian",
                            "teacher": "Test teacher 2"
                        }
                    },
                    "2": {
                        "1": {
                            "id": 12,
                            "subject": "History",
                            "teacher": "Test teacher 2"
                        },
                        "2": {
                            "id": 13,
                            "subject": "English",
                            "teacher": "Test teacher 1"
                        }
                    }
                }
            ]

## Borrowed books [GET /student/borrowed_books]
Get all borrowed books

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "title": "Book for mathematics",
                    "author": "Group of authors",
                    "get": "2015-08-10"
                }
            ]

## Attendances for student and dates [GET /student/attendances]
Get all attendances for student between two dates

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": "1",
                "start_date": "2015-10-12",
                "end_date": "2015-10-12"
            }

+ Response 200 (application/json)
    + Body

            {
                "attendance": [
                    {
                        "id": 1,
                        "subject": "Subject Name",
                        "hour": "2",
                        "justified": "yes",
                        "date": "2015-06-05"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Marks for student between two dates and subject [GET /student/marks]
Get all marks for student between two dates and subject

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": "1",
                "subject_id": "12",
                "start_date": "2015-10-12",
                "end_date": "2015-10-13"
            }

+ Response 200 (application/json)
    + Body

            {
                "marks": [
                    {
                        "id": 1,
                        "subject": "Subject Name",
                        "mark_type": "Oral",
                        "mark_value": "A+",
                        "exam": "Exam 1",
                        "date": "2015-06-10"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Exams for teacher group [GET /student/exams]
Get all exams for teacher group

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "exams": [
                    {
                        "id": 1,
                        "title": "This is title of exam",
                        "subject": "English",
                        "date": "2015-06-08"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Notices for teacher group [GET /student/notices]
Get all notices for teacher group

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "notice": [
                    {
                        "id": 1,
                        "title": "This is title of notice",
                        "subject": "English",
                        "description": "This is description of notice",
                        "date": "2015-02-02"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Dairies for student [GET /student/dairy]
Get all dairies for student

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "dairies": [
                    {
                        "id": 1,
                        "title": "This is title of notice",
                        "subject": "English",
                        "description": "This is description of notice",
                        "hour": "2",
                        "date": "2015-02-02"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Exams for student and student [GET /student/exam_subject]
Get exams for subject and student

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": "1",
                "subject_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "exams": [
                    {
                        "id": 1,
                        "title": "This is title of exam",
                        "subject": "English",
                        "description": "This is description of exam",
                        "date": "2015-02-02"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Subject list for student [GET /student/student_subject]
Get subject list for student

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "subjects": {
                    "id": 1,
                    "subject": "English",
                    "teacher": "Test Teacher",
                    "image": ""
                }
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

# Parent [/parent]
Parent endpoints, can be accessed only with role "parent"

## School year for student [GET /parent/school_years]
Get all school years with current school year name and id and other school years that he/she can select.
This method use all roles because all data(students, sections, marks, behaviors,semesters,attendances) are depend on school year

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": 1,
                "school_year": 1
            }

+ Response 200 (application/json)
    + Body

            {
                "current_school_value": "2014/2015",
                "current_school_id": 1,
                "other_school_years": {
                    "id": 1,
                    "title": "2014/2015"
                }
            }

## Timetable for student [GET /parent/timetable]
Get timetable for student with getting his token and role student
This method return array of array: first array has number of hour, first subarray is array for number of day and
in that array have objects that represent subject and teacher that teaches

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_user_id": "5",
                "school_year": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "student_groups": [
                    {
                        "id": 1,
                        "subject": "English",
                        "teacher": "Test Teacher",
                        "class": 2
                    }
                ]
            }

## Borrowed books [GET /parent/borrowed_books]
Get all borrowed books

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_user_id": "5"
            }

+ Response 200 (application/json)
    + Body

            {
                "borrowed_books": {
                    "title": "Book for mathematics",
                    "author": "Group of authors",
                    "get": "2015-08-10"
                },
                "0": {
                    "statusCode": 500,
                    "contentType": "application/json",
                    "body": {
                        "error": "not_valid_data"
                    },
                    "headers": []
                }
            }

## Attendances for student and dates [GET /parent/attendances]
Get all attendances for student between two dates

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": "1",
                "start_date": "2015-10-12",
                "end_date": "2015-10-12"
            }

+ Response 200 (application/json)
    + Body

            {
                "attendance": [
                    {
                        "id": 1,
                        "subject": "Subject Name",
                        "hour": "2",
                        "justified": "yes",
                        "date": "2015-06-05"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Marks for student between two dates and subject [GET /parent/marks]
Get all marks for student between two dates and subject

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": "1",
                "subject_id": "12",
                "start_date": "2015-10-12",
                "end_date": "2015-10-13"
            }

+ Response 200 (application/json)
    + Body

            {
                "marks": [
                    {
                        "id": 1,
                        "subject": "Subject Name",
                        "mark_type": "Oral",
                        "mark_value": "A+",
                        "exam": "Exam 1",
                        "date": "2015-06-10"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Invoices for user [GET /parent/invoices]
Get all invoices for user

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_user_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "invoices": {
                    "id": 1,
                    "amount": "10.5",
                    "title": "This is title of invoices",
                    "description": "This is description of invoices"
                }
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Children for parent [GET /parent/children]
Get all children for parent

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "user_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "children": {
                    "student_name": "Student Name",
                    "student_user_id": "1"
                }
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Exams for student [GET /parent/exams]
Get all exams for student

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "exams": [
                    {
                        "id": 1,
                        "title": "This is title of exam",
                        "subject": "English",
                        "date": "2015-06-08"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Notices for student [GET /parent/notices]
Get all notices for student

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "notice": [
                    {
                        "id": 1,
                        "title": "This is title of notice",
                        "subject": "English",
                        "description": "This is description of notice",
                        "date": "2015-02-02"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Dairies for student [GET /parent/dairy]
Get all dairies for student

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "dairies": [
                    {
                        "id": 1,
                        "title": "This is title of notice",
                        "subject": "English",
                        "description": "This is description of notice",
                        "hour": "2",
                        "date": "2015-02-02"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Exams for student and student [GET /parent/exam_subject]
Get exams for subject and student

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_id": "1",
                "subject_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "exams": [
                    {
                        "id": 1,
                        "title": "This is title of exam",
                        "subject": "English",
                        "description": "This is description of exam",
                        "date": "2015-02-02"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get student id [GET /parent/student_for_user]
Get student id for user and school year

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "user_id": "1",
                "school_year_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "student_id": "1"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

# Teacher [/teacher]
Teacher endpoints, can be accessed only with role "teacher"

## School year for user [GET /teacher/school_years]
Get all school years with current school year name and id and other school years that he/she can select.
This method use all roles because all data(students, sections, marks, behaviors,semesters,attendances) are depend on school year

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "user_id": 1,
                "school_year": 1
            }

+ Response 200 (application/json)
    + Body

            {
                "current_school_value": "2014/2015",
                "current_school_id": 1,
                "other_school_years": {
                    "id": 1,
                    "title": "2014/2015"
                }
            }

## Timetable for teacher [GET /teacher/timetable]
Get timetable for teacher with getting his token and role teacher
This method return array of array: first array has number of hour, first subarray is array for number of day and
in that array have objects that represent subject and teacher that teaches.
After first array goes second array that represents subjects and group that teacher teach in
selected school year.

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "school_year": "1"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "1": {
                        "1": {
                            "id": 10,
                            "subject": "english",
                            "group": "1 - 2"
                        },
                        "2": {
                            "id": 11,
                            "subject": "serbian",
                            "group": "2 - 2"
                        }
                    },
                    "2": {
                        "1": {
                            "id": 12,
                            "subject": "history",
                            "group": "1 - 3"
                        },
                        "2": {
                            "id": 13,
                            "subject": "english",
                            "group": "1 - 2"
                        }
                    }
                },
                [
                    {
                        "id": 4,
                        "subject": "history",
                        "group": "1 - 3"
                    },
                    {
                        "id": 1,
                        "subject": "english",
                        "group": "1 - 3"
                    }
                ]
            ]

## Timetable for teacher for selected group [GET /teacher/timetable_group]
Get timetable for teacher with getting selected group id
This method return array of array: first array has number of hour, first subarray is array for number of day and
in that array have objects that represent subject and teacher that teaches.
After first array goes second array that represents subjects and group that teacher teach in
selected group.

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_group_id": "1"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "1": {
                        "1": {
                            "id": 10,
                            "subject": "english",
                            "group": "1 - 2"
                        },
                        "2": {
                            "id": 11,
                            "subject": "serbian",
                            "group": "2 - 2"
                        }
                    },
                    "2": {
                        "1": {
                            "id": 12,
                            "subject": "history",
                            "group": "1 - 3"
                        },
                        "2": {
                            "id": 13,
                            "subject": "english",
                            "group": "1 - 2"
                        }
                    }
                },
                [
                    {
                        "id": 4,
                        "subject": "history",
                        "group": "1 - 3"
                    },
                    {
                        "id": 1,
                        "subject": "english",
                        "group": "1 - 3"
                    }
                ]
            ]

## Groups for teacher [GET /teacher/groups]
Get all groups for teacher for selected school year

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "school_year": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "student_groups": [
                    {
                        "id": 1,
                        "title": "Group 1",
                        "direction": "English",
                        "class": 2
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Notices for teacher group [GET /teacher/notices]
Get all notices for teacher group

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_group_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "notice": [
                    {
                        "id": 1,
                        "title": "This is title of notice",
                        "subject": "English",
                        "description": "This is description of notice",
                        "date": "2015-02-02"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post notice for teacher group [POST /teacher/post_notice]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_group_id": "1",
                "notice_type_id": "1",
                "subject_id": "1",
                "title": "This is title",
                "date": "2015-06-08",
                "description": "This is description"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete notice [POST /teacher/delete_notice]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "notice_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Exams for teacher group [GET /teacher/exams]
Get all exams for teacher group

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_group_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "exams": [
                    {
                        "id": 1,
                        "title": "This is title of exam",
                        "subject": "English",
                        "date": "2015-06-08"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post exam for teacher group [POST /teacher/post_exam]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_group_id": "1",
                "subject_id": "1",
                "title": "This is title",
                "date": "2015-06-08"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete exam [POST /teacher/delete_exam]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "exam_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Attendances for teacher group between two date [GET /teacher/attendances]
Get all attendances for teacher group between two date

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_group_id": "1",
                "start_date": "2015-10-12",
                "end_date": "2015-10-12"
            }

+ Response 200 (application/json)
    + Body

            {
                "attendance": [
                    {
                        "id": 1,
                        "student": "Student Name",
                        "hour": "2",
                        "justified": "yes",
                        "date": "2015-06-05"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Attendances list of hours from timetable [GET /teacher/attendance_hour_list]
Get all attendances list of hours from timetable for selected date and group

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_group_id": "1",
                "date": "2015-10-12"
            }

+ Response 200 (application/json)
    + Body

            {
                "hour_list": [
                    {
                        "id": 1,
                        "hour": "1",
                        "subject": "english"
                    },
                    {
                        "id": 2,
                        "hour": "2",
                        "subject": "history"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post attendance for student,subject and date [POST /teacher/post_attendance]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "subject_id": "1",
                "student_id": "1",
                "date": "2015-06-08",
                "hour": "2",
                "note": "This is note",
                "justified": "yes",
                "school_year_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete attendance [POST /teacher/delete_attendance]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "attendance_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Justify attendance [POST /teacher/justify_attendance]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "attendance_id": "1",
                "justify": "no/yes/unknown"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Marks for teacher group between two date [GET /teacher/marks]
Get all marks for teacher group between two date

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_group_id": "1",
                "subject_id": "1",
                "start_date": "2015-10-12",
                "end_date": "2015-10-13"
            }

+ Response 200 (application/json)
    + Body

            {
                "marks": [
                    {
                        "id": 1,
                        "student_name": "Student Name",
                        "mark_type": "Oral",
                        "mark_value": "A+",
                        "exam": "Exam 1"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post mark for student,subject and date [POST /teacher/post_mark]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "exam_id": "1",
                "mark_type_id": "1",
                "semester_id": "1",
                "student_id": 1,
                "subject_id": "1",
                "mark_value_id": "1",
                "comment": "This is comment",
                "date": "2015-06-08",
                "school_year_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete mark [POST /teacher/delete_mark]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "mark_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Students for teacher group [GET /teacher/students]
Get all students for teacher group

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_group_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "students": [
                    {
                        "id": 1,
                        "student_name": "Student Name"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Borrowed books [GET /teacher/borrowed_books]
Get all borrowed books

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "books": [
                    {
                        "user_book_id": "1",
                        "title": "Book for mathematics",
                        "author": "Group of authors",
                        "get": "2015-08-10"
                    }
                ]
            }

## Dairies for student [GET /teacher/dairy]
Get all dairies for student

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "student_group_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "diaries": [
                    {
                        "id": 1,
                        "title": "This is title of notice",
                        "subject": "English",
                        "description": "This is description of notice",
                        "hour": "2",
                        "date": "2015-02-02"
                    }
                ]
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Post dairy for subject, hour and date [POST /teacher/post_dairy]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "subject_id": "1",
                "title": "This is title",
                "date": "2015-06-08",
                "hour": "1",
                "description": "This is description"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete dairy [POST /teacher/delete_dairy]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "dairy_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

# Librarian [/librarian]
Librarian endpoints, can be accessed only with role "librarian"

## School year for user [GET /librarian/school_years]
Get all school years with current school year name and id and other school years that he/she can select.
This method use all roles because all data(students, sections, marks, behaviors,semesters,attendances) are depend on school year

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "school_year": 1
            }

+ Response 200 (application/json)
    + Body

            {
                "current_school_value": "2014/2015",
                "current_school_id": 1,
                "other_school_years": {
                    "id": 1,
                    "title": "2014/2015"
                }
            }

## Borrowed books [GET /librarian/borrowed_books]
Get all borrowed books

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "books": [
                    {
                        "user_book_id": "1",
                        "title": "Book for mathematics",
                        "author": "Group of authors",
                        "get": "2015-08-10"
                    }
                ]
            }

## Post new book [POST /librarian/add_book]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "subject_id": "1",
                "title": "Title of book",
                "author": "This is author",
                "year": "2015",
                "quantity": "5",
                "internal": "2015/15",
                "publisher": "Book publisher 2",
                "version": "0.1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Delete book [POST /librarian/delete_book]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "book_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Edit book [POST /librarian/edit_book]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "book_id": "1",
                "subject_id": "1",
                "title": "Title of book",
                "author": "This is author",
                "year": "2015",
                "quantity": "5",
                "internal": "2015/15",
                "publisher": "Book publisher 2",
                "version": "0.1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Reserved books [GET /librarian/reserved_books]
Get all reserved books

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "books": {
                    "id": "1",
                    "title": "Book for mathematics",
                    "author": "Group of authors",
                    "subject": "Mathematics",
                    "reserved": "2015-08-10"
                }
            }

## Delete reserve book [POST /librarian/delete_reserved_book]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "user_book_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Issue reserved book [POST /librarian/issue_reserved_book]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "user_book_id": "1",
                "get": "2015-06-08"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Issue book [POST /librarian/issue_book]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "book_id": "1",
                "user_id": "1",
                "note": "This is note",
                "date": "2015-02-02"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Return ook [POST /librarian/return_book]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "user_book_id": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "success": "success"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

## Get list of subjects [GET /librarian/subject_list]
Get list of subjects for all directions and class use for creating book

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "subjects": [
                    {
                        "id": "1",
                        "title": "Direction2 (3) English",
                        "direction": "Direction2",
                        "class": "3",
                        "subject": "English"
                    }
                ]
            }

## Get list of users [GET /librarian/user_list]
Get list of users for issuing book

+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "users": [
                    {
                        "id": "1",
                        "name": "First Last name",
                        "role": "teacher|librarian|admin|student|parent"
                    }
                ]
            }