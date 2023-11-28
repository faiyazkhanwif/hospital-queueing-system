# Hospital Queuing System Simulation

## Introduction
This project simulates a hospital queuing system consisting of two main components: patients queuing up and doctors treating patients. The underlying data structure utilized is a custom-built queue, with no reliance on pre-existing libraries.

## Algorithm Explanation

Patients are enqueued until the number of patients reaches or exceeds half of the maximum size. Once the queue surpasses half the maximum size, the next patient is enqueued in the first queue. Simultaneously, the second last patient of the first queue is shifted to the second queue, and the last patient of the first queue moves up one space. The first queue pointer is then reset to null, and the second queue pointer is incremented. This process continues until both queues are half full.
When both pointers align at the same level in their respective queues, the next patient is enqueued in the second queue, and the first array pointer is incremented. The cycle continues until both arrays reach the maximum limit.

If, for instance, a doctor chooses to treat five patients at a time, the algorithm specifies that if the number of patients in the first queue is greater than maxSize - 5 and the second queue is at its maximum capacity, then Doctor 1 proceeds to treat the first five patients from the first queue. This process iterates until five patients have been treated from the first queue.

Similarly, if the number of patients in the first queue is equal to maxSize - 5 and the second queue has more than five patients, Doctor 2 takes over after Doctor 1 has finished treating the first five patients from the first queue. Doctor 2 then treats the initial five patients from the second queue, and this process continues until five patients have been treated from the second queue.

Once these sequential steps are completed, both doctors concurrently treat patients until there are no remaining patients in either queue. The simultaneous treatment continues until both queues are empty. The number '5' here represents the scenario where the doctor decides to treat five patients from a queue at a time.

## Extra Methods
Two additional methods, displayBothQinfo() and areBothQempty(), have been incorporated to enhance functionality.

- #### displayBothQinfo():
    This method provides comprehensive information about the patients in the queues after the enqueuing process. The information is displayed sequentially by gender, age, and illness.

- #### areBothQempty()
    This method checks whether both queues are empty. If both queues are devoid of patients, it returns true; otherwise, it returns false.
