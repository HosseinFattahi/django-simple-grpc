# django-simple-grpc

**django-simple-grpc** is a developer-friendly Django package that makes using gRPC in Django **simple, fast, and automatic**.

It supports both server and client code, and includes powerful Django management commands for generating `.proto` files and gRPC services from your existing models.

---

## 🚀 Features

- ✅ Auto-generate `.proto` files from Django models
- ✅ Compile `.proto` files to Python gRPC stubs using `grpcio-tools`
- ✅ Run gRPC servers using a clean `run_grpc` command
- ✅ Build gRPC clients easily with `GRPCClient`
- ✅ Works with Django 3.2+ (up to 5.x)
- ✅ Compatible with Python 3.7–3.12

---

## 📦 Installation

```bash
pip install django-simple-grpc

⚙️ Setup in Django

Add to your `settings.py`:

```python
INSTALLED_APPS = [
    ...
    "django_simple_grpc",
]

Then add the gRPC configuration:

```python
GRPC_SERVER_PORT = 50051
GRPC_SERVER_ADDRESS = "localhost:50051"

# Replace <your_app> and <YourServiceName> with your actual values
GRPC_SERVICE_REGISTER = "grpc_generated.<your_app>_pb2_grpc.add_<YourServiceName>Servicer_to_server"
GRPC_SERVICE_IMPL = "<your_app>.grpc_service.<YourServiceName>Servicer"


🔁 Example if your app is called store and your service is ProductService:

```python
GRPC_SERVICE_REGISTER = "grpc_generated.store_pb2_grpc.add_ProductServiceServicer_to_server"
GRPC_SERVICE_IMPL = "store.grpc_service.ProductServiceServicer"
