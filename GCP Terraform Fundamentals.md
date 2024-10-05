GCP Terraform Fundamentals

Download and install the provider binary:

    terraform init

Create an execution plan:

    terraform plan

In the same directory as the instance.tf file you created, run this command:

    terraform apply

In Cloud Shell, inspect the current state:

    terraform show

In Cloud Shell, create an empty configuration file named instance.tf with the following command:

    vi instance.tf

Example: .tf

    resource "google_compute_instance" "terraform" {
      project      = "qwiklabs-gcp-00-d6e492ac13c4"
      name         = "terraform"
      machine_type = "e2-medium"
      zone         = "us-central1-f"
    
      boot_disk {
        initialize_params {
          image = "debian-cloud/debian-11"
        }
      }
    
      network_interface {
        network = "default"
        access_config {
        }
      }
    }
