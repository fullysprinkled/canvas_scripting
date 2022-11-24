import requests
import time

cookies = {
    'log_session_id': 'bla',
    '_gid': 'bla',
    '_ga': 'bla',
    '_legacy_normandy_session': 'bla',
    'canvas_session': 'bla',
    '_ga_0ZABCDEFXYZ': 'bla',
    '_csrf_token': 'bla',
}

headers = {
    'authority': 'urschool.instructure.com',
    'accept': 'application/json, text/javascript, application/json+canvas-string-ids, */*; q=0.01',
    'accept-language': 'en-US,en;q=0.9',
    'content-type': 'application/x-www-form-urlencoded; charset=UTF-8',
    'origin': 'https://school_name.instructure.com',
    'referer': 'https://school_name.instructure.com/courses/course_number/gradebook/speed_grader?assignment_id=01234&student_id=00001',
    'sec-ch-ua': '"Chromium";v="106", "Google Chrome";v="106", "Not;A=Brand";v="99"',
    'sec-ch-ua-mobile': '?0',
    'sec-ch-ua-platform': '"macOS"',
    'sec-fetch-dest': 'empty',
    'sec-fetch-mode': 'cors',
    'sec-fetch-site': 'same-origin',
    'user-agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/106.0.0.0 Safari/537.36',
    'x-csrf-token': 'bla',
    'x-requested-with': 'XMLHttpRequest',
}

graded_log = []

count = 0
for assignment in student_grades_by_assignment.keys():
    for student in student_ids:
        count+=1
        time.sleep(0.2)
        grade=student_grades_by_assignment[assignment][student]
        data = {
            'submission[assignment_id]': assignment,
            'submission[user_id]': student,
            'submission[graded_anonymously]': 'false',
            'submission[grade]': grade,
            '_method': 'POST',
            'authenticity_token': 'bla',
        }
        update_submission_response = requests.post('https://school_name.instructure.com/courses/course_number/gradebook/update_submission', cookies=cookies, headers=headers, data=data)
        r = update_submission_response
        rj = update_submission_response.json()
        print(count, assignment, student, grade, r)
        graded_log.append(
            [str(r)
            , rj[0]['submission']['user_id']
            , rj[0]['submission']['grade']
            , rj[0]['submission']['grade_matches_current_submission']
            , rj[0]['submission']['graded_at']
            , rj[0]['submission']['assignment_id']])
            
