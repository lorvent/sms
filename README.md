FORMAT: 1A

# ALIBlueprint

# AppHttpControllersApiAuthController

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
                "token": "token"
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

## Get role for authenticated user [GET /role]


+ Request (application/json)
    + Body

            {
                "token": "foo"
            }

+ Response 200 (application/json)
    + Body

            {
                "role": "role"
            }

+ Response 400 (application/json)
    + Body

            {
                "error": "no_role"
            }

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

# AppHttpControllersApiGeneralController

## School year for user [GET /school_years]
Get all school years with current school year name and id and other school years that he/she can select.

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

## Behaviors [GET /behaviors]
Get all behaviors

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
                    "year": "2015"
                },
                {
                    "id": "2",
                    "subject": "English",
                    "title": "English 2",
                    "author": "Group of authors",
                    "year": "2015"
                }
            ]

## Directions [GET /directions]
Get all directions

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

+ Request (application/json)
    + Body

            {
                "token": "foo",
                "direction": "1"
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
Get all transportations

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
Get all transportation directions for selected transportation

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
Get all messages

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

## Send message to user [POST /send_message]
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
Get all users

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
Reserve book from user

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
Get all payments for user

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

## Get student for user and school year [GET /student]


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

# AppHttpControllersApiParentController

## Timetable for student [GET /student/timetable]
Get timetable for student with getting his token and role student
This method return array of array: first array has number of hour, first subarray is array for number of day and
in that array have objects that represent subject and teacher that teaches

+ Request (application/json)
    + Body

            {
                "token": "foo"
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

            [
                {
                    "title": "Book for mathematics",
                    "author": "Group of authors",
                    "get": "2015-08-10"
                },
                {
                    "statusCode": 500,
                    "contentType": "application/json",
                    "body": {
                        "error": "not_valid_data"
                    },
                    "headers": []
                }
            ]

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
                        "subject": "Subject Name",
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

## Invoices for user [GET /parent/invoices]
Get all invoices for user

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
                    "title": "This is title of invoices",
                    "description": "This is description of invoices"
                }
            ]

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

            [
                {
                    "id": 1,
                    "student_name": "Student Name",
                    "student_user_id": "1"
                }
            ]

+ Response 500 (application/json)
    + Body

            {
                "error": "not_valid_data"
            }

# AppHttpControllersApiStudentController

## Timetable for student [GET /student/timetable]
Get timetable for student with getting his token and role student
This method return array of array: first array has number of hour, first subarray is array for number of day and
in that array have objects that represent subject and teacher that teaches

+ Request (application/json)
    + Body

            {
                "token": "foo"
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
                        "subject": "Subject Name",
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

# AppHttpControllersApiTeacherController

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
                "notice": [
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
                        "hour": "1"
                    },
                    {
                        "id": 2,
                        "hour": "2"
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
                "justified": "yes"
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
                "notice": [
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

            [
                {
                    "title": "Book for mathematics",
                    "author": "Group of authors",
                    "get": "2015-08-10"
                }
            ]

# AppHttpControllersApiLibrarianController

## Borrowed books [GET /librarian/borrowed_books]
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

## Post new book [POST /librarian/post_book]


+ Request (application/json)
    + Body

            {
                "token": "foo",
                "subject_id": "1",
                "title": "Title of book",
                "author": "This is author",
                "year": "2015",
                "quantity": "5"
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

## Reserved books [GET /librarian/reserved_books]
Get all reserved books

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
                    "title": "Book for mathematics",
                    "author": "Group of authors",
                    "reserved": "2015-08-10"
                }
            ]

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
                "note": "This is note"
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
