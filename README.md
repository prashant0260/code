hx# code
5
<!DOCTYPE html>
<html>
<head>
    <title>Simple Bootstrap Page</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Bootstrap -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
</head>

<body>

<!-- Navbar -->
<nav class="navbar navbar-dark bg-dark">
    <div class="container">
        <span class="navbar-brand">My Site</span>
    </div>
</nav>

<!-- Content -->
<div class="container text-center mt-4">
    <h2 class="text-primary">Welcome</h2>

    <!-- Buttons -->
    <button class="btn btn-primary">Primary</button>
    <button class="btn btn-success">Success</button>

    <!-- Form -->
    <form class="mt-3">
        <input type="text" class="form-control mb-2" placeholder="Enter Name">
        <input type="email" class="form-control mb-2" placeholder="Enter Email">
        <button class="btn btn-danger">Submit</button>
    </form>
</div>

</body>
</html>
