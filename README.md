class Student:
    def __init__(self, name, surname, gender, hw_gr):
        self.name = name
        self.surname = surname
        self.gender = gender
        self.finished_courses = []
        self.courses_in_progress = []
        self.grades = {}
        self.hw_gr = hw_gr

    def hw_gr(self):
        sum_gr = 0
        len_gr = 0
        for course in self.grades.values():
            sum_gr += sum(course)
            len_gr += len(course)
            homework_grade = round(sum_gr / len_gr)

    def __str__(self):
        return f"Имя: {self.name} \nФамилия: {self.surname} \nСредняя оценка за домашние задания: {self.hw_gr()}"

    def rate_hw(self, lecturer, course, grade):
        marks = [0,1,2,3,4,5,6,7,8,9,10]
        lecturer1 = Lecturer("Ivan", "Petrov")
        student1.rate_hw(lecturer1,"Sql",9)
        if isinstance(lecturer, Lecturer) and course in self.courses_attached and course in lecturer.courses_in_progress:
#        if isinstance(lecturer, Lecturer) and grade in marks:
            if course in lecturer.grades:
                lecturer.grades[course] += [grade]
            else:
                lecturer.grades[course] = [grade]
        else:
            return 'Ошибка'



class Mentor:
    def __init__(self, name, surname):
        self.name = name
        self.surname = surname
        self.courses_attached = []

class Lecturer(Mentor):
    def __init__(self, name, surname, av_gr):
        self.grades = {}
        self.name = name
        self.surname = surname
        self.av_gr = av_gr

    def av_gr(self):
        sum_gr = 0
        len_gr = 0
        for course in self.grades.values():
            sum_gr += sum(course)
            len_gr += len(course)
            average_grade = round(sum_gr / len_gr)

    def __str__(self):
        return f"Имя: {self.name} \nФамилия: {self.surname} \nСредняя оценка за лекции: {self.av_gr()}"

class Reviewer(Mentor):
    def __init__(self, name, surname):
        self.name = name
        self.surname = surname

    def rate_hw(self, student, course, grade):
        marks = [0,1,2,3,4,5,6,7,8,9,10]
        if isinstance(student, Student) and course in self.courses_attached and course in student.courses_in_progress:
#        if isinstance(lecturer, Lecturer) and grade in marks:
            if course in student.grades:
                student.grades[course] += [grade]
            else:
                student.grades[course] = [grade]
        else:
            return 'Ошибка'

    def __str__(self):
        return f"Имя: {self.name} \nФамилия: {self.surname}"

best_student = Student('Ruoy', 'Eman', 'your_gender')
best_student.courses_in_progress += ['Python']

cool_mentor = Mentor('Some', 'Buddy')
cool_mentor.courses_attached += ['Python']

cool_mentor.rate_hw(best_student, 'Python', 10)
cool_mentor.rate_hw(best_student, 'Python', 10)
cool_mentor.rate_hw(best_student, 'Python', 10)

print(best_student.grades)
print(some_reviewer)
print(some_lecturer)
print(some_student)