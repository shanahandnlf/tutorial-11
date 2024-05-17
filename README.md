Reflection on Hello Minikube

Answer the following questions to guide your reflection:
1. Compare the application logs before and after you exposed it as a Service.
Try to open the app several times while the proxy into the Service is running.
What do you see in the logs? Does the number of logs increase each time you open the app?

Sebelom diekspos:
![alt text](image.png)

Setelah diekspos:
![alt text](image-1.png)

Gambar di atas merupakan percobaan saya saat melakukan pengecekan log. Iya terdapat perbedaan setelah service diekspos. Setelah service diekspos, log akan terus bertambah setiap kali aplikasi diakses. Contohnya seperti jika saya melakukan refresh pada aplikasi, maka log akan bertambah. Sebelom diekspos, log hanya berisi informasi terkati http dan udp server pada port 8080. 

2. Notice that there are two versions of `kubectl get` invocation during this tutorial section.
The first does not have any option, while the latter has `-n` option with value set to
`kube-system`.
What is the purpose of the `-n` option and why did the output not list the pods/services that you
explicitly created?
> Hint: Do some reading about [Namespace in Kubernetes
documentation](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces
/).

`-n` option digunakan untuk menentukan namespace yang akan diakses. Namespace adalah cara untuk memisahkan resource pada kubernetes. Jadinya, kita bisa mengakses resource pada namespace tertentu. Jika tidak menggunakan `-n` option, maka akan mengakses default namespace. Jadi, resource yang diakses adalah resource pada default namespace saja. 
