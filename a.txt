Write a Go program to print “Hello, world!” on the screen. Compile and run the 
program.  
 
 
package main 
import "fmt" 
func main() { 
 fmt.Println("Hello, World!") 
}






















Write a Go a program that shows your name and address.  
 
package main 
import "fmt" 
func main() { 
 fmt.Println("Nitte Meenakshi Institute of Technology ") 
 fmt.Println("P.B.No.6429. ") 
 fmt.Println("Yelahanka, Bangalore 560064") 
 fmt.Println(" Karnataka, India") 
} 

























 
package main 
 
import "fmt" 
 
func main() { 
 fmt.Println("NMIT")             
 fmt.Println("NMIT is  my college")     
  
}


















Write a Go a program to get a number from the console and check if it’s between 1 and 
10. 

 
package main 
 
import ( 
 "fmt" 
) 
 
func main() { 
 var number int 
 
 fmt.Print("Enter a number: ") 
 _, err := fmt.Scanf("%d", &number) 
 if err != nil { 
  fmt.Println("Invalid input. Please enter a valid number.") 
  return 
 } 
 
 if number >= 1 && number <= 10 { 
  fmt.Println("The number is between 1 and 10.") 
 } else { 
  fmt.Println("The number is not between 1 and 10.") 
 } 
}











Write a Go a program which creates an array with the number 0 to 10.  
 
 
package main 
 
import ( 
 "fmt" 
) 
 
func main() { 
 // Create an array with numbers from 0 to 10 
 var numbers [11]int 
 
 for i := 0; i <= 10; i++ { 
  numbers[i] = i 
 } 
 
 // Print the array 
 fmt.Println("Array of numbers from 0 to 10:") 
 for _, num := range numbers { 
  fmt.Println(num) 
 } 
} 





Write a Go a program that counts from 1 to 10.  
 
 
package main 
 
import "fmt" 
 
func main() { 
 var sum float32 = 0 
 var i float32 = 1 
 for i <= 10 { 
  sum = sum + i 
  i = i + 1 
 } 
 fmt.Println("sum of 1 to 10 numbers is ", sum) 
}














Write a program which prompts the user to enter a floating-point number and prints the 
integer which is a truncated version of the floating-point number that was entered. 
Truncation is the process of removing the digits to the right of the decimal place.  
 
 
package main 
 
import "fmt" 
 
func main() { 
 var f float64 
 fmt.Println("Enter a float:") 
 fmt.Scanln(&f) 
 
 i := int(f) 
 fmt.Println("Truncated integer:", i) 
} 






















 
Write a program which prompts the user to enter a string. The program searches 
through the entered string for the characters ‘I’, ‘a’, and ‘n’. The program should print 
“Found!” if the entered string starts with the character ‘I’, ends with the character ‘n’, 
and contains the character ‘a’. The program should print “Not Found!” otherwise. The 
program should not be case-sensitive, so it does not matter if the characters are upper
case or lower-case.  
 
 
 
package main 
 
import ( 
 "fmt" 
 "strings" 
) 
 
func main() { 
 str := "I am a batman" 
 if strings.HasPrefix(str, "I") && strings.HasSuffix(str, "n") && strings.Contains(str, 
"a") { 
  fmt.Println("String found", str) 
 } else { 
  fmt.Println("String not found", str) 
 } 
}





















 
Write a Go a program to check if a file exists on your local 
disk or not. 





package main

import (
	"fmt"
	"os"
)

func main() {
	filepath := "lab/a.txt"

	if _, err := os.Stat(filepath); os.IsNotExist(err) {
		fmt.Println("File does not exist")
	} else if err != nil {
		fmt.Println("Error")
	} else {
		fmt.Println("File exists")
	}
}
















Write a Go a program to write a list of cities to a new file. 








package main

import (
	"fmt"
	"os"
)

func main() {
	cities := []string{
		"Banda",
		"Kanpur",
		"Lucknow",
		"Mau",
		"Delhi",
	}

	file, err := os.Create("city.txt")
	if err != nil {
		panic(err)
	}
	defer file.Close()

	for _, city := range cities {
		fmt.Fprintf(file, "%s\n", city)
	}
	fmt.Println("Saved successfully")
}











Write a Go a program that takes the string ‘hello world’ and slice it in two 


package main

import (
	"fmt"
)

func main() {
	str := "hello world"
	mid := len(str) / 2

	first := str[:mid]
	last := str[mid:]

	fmt.Println(first, last)
}

















 
Write a Go a program which creates a method that sums two numbers. 





package main

import (
	"fmt"
)

func add(a int, b int) int {
	return a + b
}
func main() {
	var a, b int
	fmt.Println("Enter a: ")
	fmt.Scan(&a)
	fmt.Println("Enter b: ")
	fmt.Scan(&b)
	r := add(a, b)
	fmt.Println(r)
}










Write a Go a program which creates a method that calls 
another method. 

package main

import (
	"fmt"
)

func add(a int, b int) int {
	return a + b
}

func result(a int, b int) {
	result := add(a, b)
	fmt.Println(result)
}
func main() {
	var a, b int
	fmt.Println("Enter a: ")
	fmt.Scan(&a)
	fmt.Println("Enter b: ")
	fmt.Scan(&b)
	result(a, b)

}


















Write a Go program which prompts the user to enter integers and stores the integers in 
a sorted slice. The program should be written as a loop. Before entering the loop, the 
program should create an empty integer slice of size (length) 3. During each pass 
through the loop, the program prompts the user to enter an integer to be added to the 
slice. The program adds the integer to the slice, sorts the slice, and prints the contents of 
the slice in sorted order. The slice must grow in size to accommodate any number of 
integers which the user decides to enter. The program should only quit (exiting the loop) 
when the user enters the character ‘X’ instead of an integer.



package main

import (
	"fmt"
	"sort"
)

func main() {
	numbers := []int{}
	for {
		var input string
		fmt.Println("Enter a number or X")
		fmt.Scan(&input)

		if input == "X" || input == "x" {
			break
		}

		var number int
		_, err := fmt.Sscanf(input, "%d", &number)
		if err != nil {
			fmt.Println("Error: ", err)
			continue
		}
		numbers = append(numbers, number)
		sort.Ints(numbers)
		fmt.Println(numbers)
	}
}




















Write a Go program which prompts the user to first enter a name, and then enter an 
address. Your program should create a map and add the name and address to the map 
using the keys “name” and “address”, respectively. Your program should use Marshal() 
to create a JSON object from the map, and then your program should print the JSON 
object. 

package main

import (
	"encoding/json"
	"fmt"
)

func main() {
	data := make(map[string]string)

	fmt.Println("Enter the name")
	var name string
	fmt.Scan(&name)

	fmt.Println("Enter the address")
	var address string
	fmt.Scan(&address)

	data["name"] = name
	data["address"] = address

	jsondata, err := json.Marshal(data)
	if err != nil {
		fmt.Println("Something went wrong")
	}
	fmt.Println(string(jsondata))

}

