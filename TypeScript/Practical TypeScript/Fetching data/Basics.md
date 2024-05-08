```ts
const url = 'https://www.course-api.com/react-tours-project';  
  
type Tour = {  
    id: string;  
    name: string;  
    info: string;  
    image: string;  
    price: string;
};  

// it is SUPER IMPORTANT to ALWAYS set the Promise type return as generic and specify the type when dealing with fetch, axios etc.!!
async function fetchData(url: string): Promise<Tour[]> {
    try {  
       const response = await fetch(url);  
       if (!response.ok) {  
          throw new Error(`HTTP error! status: ${response.status}`);  
       }  
  
       const data: Tour[] = await response.json();  
       console.log(data);  
       return data;  
    } catch (error) {  
       const errorMsg = 
	       error instanceof Error ? error.message : 'there was an error...';  
       console.error(errorMsg);  
  
       return [];  
    }  
}  
  
const tours = await fetchData(url);  
  
tours.map((tour: any) => {  
    console.log(tour.name);  
});

```

What if we would like to extend the type Tour in the example above with more properties? TS itself will not be able to validate them at runtime. But there is a solution with the Zod library.

Zod is a TypeScript-first schema declaration and validation library. Thanks to Zod we get the validation not only at build time but also at runtime.

- [Zod](https://zod.dev/)  
- [Error Handling in Zod](https://zod.dev/ERROR_HANDLING)

run `npm install zod`

#### Example usage:

```ts
import { z } from 'zod';  
  
const url = 'https://www.course-api.com/react-tours-project';  
  
const tourSchema = z.object({  
    id: z.string(),  
    name: z.string(),  
    info: z.string(),  
    image: z.string(),  
    price: z.string(),  
    something: z.number() // if this prop will not be returned with the object  
    // zod will throw an error in the console with details});  
  
type Tour = z.infer<typeof tourSchema>;  
  
async function fetchData(url: string): Promise<Tour[]> {  
    try {  
       const response = await fetch(url);  
       if (!response.ok) {  
          throw new Error(`HTTP error! status: ${response.status}`);  
       }  
  
       const rawData: Tour[] = await response.json();  
  
       const result = tourSchema.array().safeParse(rawData);  
  
       console.log(result); // now this will return an object with status  
  
       if (!result.success) {  
          throw new Error(`Invalid data: ${result.error}`);  
       }  
  
       return result.data;  
    } catch (error) {  
       const errorMsg = 
	       error instanceof Error ? error.message : 'there was an error...';  
       console.error(errorMsg);  
  
       return [];  
    }  
}  
  
const tours = await fetchData(url);  
  
tours.map((tour: any) => {  
    console.log(tour.name);  
});
```