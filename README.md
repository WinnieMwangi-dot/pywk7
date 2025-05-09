
class Smartphone:
    def __init__(self, brand, model, storage, battery_capacity, os):
        self.brand = brand
        self.model = model
        self.storage = storage
        self.battery_capacity = battery_capacity
        self.os = os
    
    def call(self, contact):
        print(f"Calling {contact} from {self.model}... 📞")
    
    def browse(self, website):
        print(f"Browsing {website} on {self.model}... 🌐")
    
    def get_info(self):
        return f"{self.brand} {self.model} | Storage: {self.storage}GB | Battery: {self.battery_capacity}mAh | OS: {self.os}"

# Inheritance and Encapsulation
class SmartphonePro(Smartphone):
    def __init__(self, brand, model, storage, battery_capacity, os, camera_quality, water_resistant):
        super().__init__(brand, model, storage, battery_capacity, os)
        self.__camera_quality = camera_quality   # Encapsulated attribute
        self.__water_resistant = water_resistant

    def get_pro_info(self):
        base_info = super().get_info()
        water_status = "Yes" if self.__water_resistant else "No"
        return f"{base_info} | Camera: {self.__camera_quality}MP | Water Resistant: {water_status}"

    # Encapsulation through getter
    def get_camera_quality(self):
        return self.__camera_quality
    
    # Encapsulation through setter
    def set_camera_quality(self, new_quality):
        if new_quality > 0:
            self.__camera_quality = new_quality
        else:
            print("Invalid camera quality value!")

# Activity 2: Polymorphism Challenge
class Vehicle:
    def move(self):
        pass  # Base class does not define a specific move behavior.

class Car(Vehicle):
    def move(self):
        print("Driving... 🚗")

class Plane(Vehicle):
    def move(self):
        print("Flying... ✈️")

class Boat(Vehicle):
    def move(self):
        print("Sailing... ⛵")

# Polymorphic behavior demonstration
vehicles = [Car(), Plane(), Boat()]
for vehicle in vehicles:
    vehicle.move()  # Each move method is called based on the type of vehicle
