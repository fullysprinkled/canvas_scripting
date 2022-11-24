## Description 
I've seen a lot of TAs have to manually input this stuff from another spreadsheet for hours, that's a total waste of time. 
 This simple request loop can be used to grade several assignments in a course given a list of students. 
 This just to prove that Canvas has an internal API that can be used for automation certain tasks. 
 To get started replace the bla strings and ID number placeholders: 
 1.  Replace all the cookies and 'x-csrf-token' header value with data from your logged in browser session. 
 2.  Replace the URL with your institution's url
 3.  Replace the course number with your course's course id (found like --> courses/012345)
 
## Future improvements: 
- import cookies from browser automatically 
- ability to parse grades from csv files 
- scraper for student institution id and user_id lists from users page of courses
- ability to grade multiple classes in multiple courses with differing students, automatically create datastructures holding student info by course
