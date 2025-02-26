# exam-marks
def calculate_grade(mean_mark):
    """Calculate the grade based on the mean mark."""
    if mean_mark > 70:
        return "A"
    elif mean_mark > 60:
        return "B"
    elif mean_mark > 50:
        return "C"
    elif mean_mark > 40:
        return "D"
    else:
        return "F"

def main():
    marks = []
    
    while True:
        mark_input = input("Enter a mark (or press Enter to finish): ")
        
        if mark_input == "":
            break  # Exit the loop if the user presses Enter
        
        try:
            mark = int(mark_input)
            if 0 <= mark <= 100:
                marks.append(mark)
            else:
                print("Please enter a mark between 0 and 100.")
        except ValueError:
            print("Invalid input. Please enter a valid integer.")
    
    if marks:
        highest = max(marks)
        lowest = min(marks)
        mean = sum(marks) / len(marks)
        grade = calculate_grade(mean)
        
        print(f"\nHighest mark: {highest}")
        print(f"Lowest mark: {lowest}")
        print(f"Mean mark: {mean:.2f}")
        print(f"Grade: {grade}")
    else:
        print("No marks were entered.")

if __name__ == "__main__":
    main()
