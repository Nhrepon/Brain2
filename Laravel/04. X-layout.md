layout.blade.php
```html
<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Document</title>

    @vite('resources/css/app.css')

</head>

<body>

    <div class="container mx-auto">

    <h1 class="text-4xl font-bold text-red-600"> Hello world .... </h1>

    {{$slot}}

    </div>

</body>

</html>
```

index.blade.php
```html
<x-layout>

    <div>

        <h1 class="text-2xl">Total task: {{ $tasks->count() }}</h1>

    </div>

    <x-task-status :status="request()->get('status')"/>

  

    @foreach ($tasks as $task)

        <!-- <x-task :task="$task" /> -->

        <x-task :$task />

    @endforeach

</x-layout>
```