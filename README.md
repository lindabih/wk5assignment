# wk5assignment
week 5 assignment OOP


class Book:
    def __init__(self, title, author, pages):
        self.title = title
        self.author = author
        self.pages = pages
        self._is_checked_out = False  # Encapsulated attribute

    def read(self):
        return f"Reading '{self.title}' by {self.author}."

    def check_out(self):
        if not self._is_checked_out:
            self._is_checked_out = True
            return f"'{self.title}' has been checked out."
        return f"'{self.title}' is already checked out."

    def return_book(self):
        if self._is_checked_out:
            self._is_checked_out = False
            return f"'{self.title}' has been returned."
        return f"'{self.title}' was not checked out."

    def is_checked_out(self):
        return self._is_checked_out

# Inheritance layer
class EBook(Book):
    def __init__(self, title, author, pages, file_size_mb):
        super().__init__(title, author, pages)
        self.file_size_mb = file_size_mb

    def download(self):
        return f"Downloading '{self.title}' ({self.file_size_mb}MB)..."

    # Polymorphism: override read method
    def read(self):
        return f"Reading '{self.title}' on your device."

# Example usage
if __name__ == "__main__":
    physical_book = Book("1984", "George Orwell", 328)
    ebook = EBook("Digital Fortress", "Dan Brown", 356, 2.5)

    print(physical_book.read())
    print(physical_book.check_out())
    print(physical_book.return_book())

    print(ebook.download())
    print(ebook.read())


    #question2
    class Car:
    def move(self):
        print("Driving 🚗")

class Plane:
    def move(self):
        print("Flying ✈️")

class Boat:
    def move(self):
        print("Sailing 🚤")

# List of vehicles
vehicles = [Car(), Plane(), Boat()]

for vehicle in vehicles:
    vehicle.move()
