<div dir="rtl">

# الگوریتم مرتب سازی حبابی

در این آموزش ، نحوه عملکرد مرتب سازی حبابی را خواهید آموخت.

## مرتب سازی حبابی چگونه کار می کند؟
با شروع از شاخص اول ، عناصر اول و دوم را مقایسه کنید. اگر عنصر اول بزرگتر از عنصر دوم باشد ، آنها عوض می شوند.
اکنون ، عناصر دوم و سوم را مقایسه کنید. اگر مرتب نیستند آنها را عوض کنید.
روند فوق تا آخرین عنصر ادامه دارد.

</div>


### الگوریتم مرتب سازی حبابی

```

bubbleSort(array)
  for i <- 1 to indexOfLastUnsortedElement-1
    if leftElement > rightElement
      swap leftElement and rightElement
end bubbleSort
```

### الگوریتم مرتب سازی حبابی در پایتون
```
# Bubble sort in Python

def bubbleSort(array):
    
    # run loops two times: one for walking throught the array 
    # and the other for comparison
    for i in range(len(array)):
        for j in range(0, len(array) - i - 1):

            # To sort in descending order, change > to < in this line.
            if array[j] > array[j + 1]:
                
                # swap if greater is at the rear position
                (array[j], array[j + 1]) = (array[j + 1], array[j])


data = [-2, 45, 0, 11, -9]
bubbleSort(data)
print('Sorted Array in Asc ending Order:')
print(data)
```


<div dir="rtl">
 
 ### الگوریتم مرتب سازی حبابی بهینه شده


در کد بالا ، تمام مقایسه های ممکن حتی اگر آرایه مرتب شده باشد انجام می شود. زمان اجرا را افزایش می دهد.

کد را می توان با معرفی یک متغیر اضافی مبادله شده بهینه کرد. پس از هر بار تکرار ، اگر مبادله ای انجام نشود ، دیگر نیازی به انجام حلقه های بعدی نیست.

در چنین حالتی ، متغیر مبادله نادرست تنظیم می شود. بنابراین ، می توانیم از تکرارهای بعدی جلوگیری کنیم.

الگوریتم زیر برای مرتب سازی حباب بهینه شده است
</div>

###  الگوریتم حبابی  با استفاده ازمتغیر(swapped)
```
bubbleSort(array)
  swapped <- false
  for i <- 1 to indexOfLastUnsortedElement-1
    if leftElement > rightElement
      swap leftElement and rightElement
      swapped <- true
end bubbleSort
```

### الگوریتم مرتب سازی حبابی بهینه شده
```
# Bubble sort in Python

def bubbleSort(array):
    
    # Run loops two times: one for walking throught the array
    # and the other for comparison
    for i in range(len(array)):
        
        # swapped keeps track of swapping
        swapped = True
        for j in range(0, len(array) - i - 1):

            # To sort in descending order, change > to < in this line.
            if array[j] > array[j + 1]:

                # Swap if greater is at the rear position
                (array[j], array[j + 1]) = (array[j + 1], array[j])
                swapped = False
                
        # If there is not swapping in the last swap, then the array is already sorted.
        if swapped:
            break


data = [-2, 45, 0, 11, -9]
bubbleSort(data)
print('Sorted Array in Ascending Order:')
print(data)
```
<div dir="rtl">

###### پیچیدگی
مرتب سازی حباب یکی از ساده ترین الگوریتم های مرتب سازی است. دو حلقه در الگوریتم اجرا شده است
تعداد مقایسه
</div>

```

(n - 1) + (n - 2) + (n - 3) +.....+ 1 = n(n - 1) / 2

```
<div dir="rtl">
 
###### پیچیدگی: O (n2)

همچنین ، ما می توانیم پیچیدگی را به سادگی با مشاهده تعداد حلقه ها تجزیه و تحلیل کنیم. 2 حلقه وجود دارد بنابراین پیچیدگی n * n = n2 است

###### پیچیدگی بدترین حالت: O (n2)
اگر بخواهیم به ترتیب صعودی مرتب شویم و آرایه به ترتیب نزولی باشد ، بدترین حالت رخ می دهد.

###### پیچیدگی بهترین حالت: O (n)
اگر آرایه از قبل مرتب شده باشد ، دیگر نیازی به مرتب سازی نیست.

###### پیچیدگی حالت میانگین: O (n2)
زمانی اتفاق می افتد که عناصر آرایه به ترتیب بهم ریخته (نه صعودی و نه نزولی) باشند.

###### پیچیدگی فضا:O(1)
زیرا از یک  متغیر اضافی برای مبادله استفاده می شود.
###### پیچیدگی فضا در االگوریتم بهینه سازی شده :O(2)
متغیرswapp بر پیچیدگی افزوده
آن را O(2)می کند
</div>
