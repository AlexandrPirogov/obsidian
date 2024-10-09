Terraform содержит конфигурацию во множестве файлов, хранящийся в отдельной директории. 

```bash
terraform {
  required_providers {
    oci = {
      source = "oracle/oci"
    }
  }
}

provider "oci" {
  region              = "us-sanjose-1"
  auth                = "SecurityToken"
  config_file_profile = "learn-terraform"
}

resource "oci_core_vcn" "internal" {
  dns_label      = "internal"
  cidr_block     = "172.16.0.0/20"
  compartment_id = "<your_compartment_OCID_here>"
  display_name   = "My internal VCN"
}

```

# Основные блоки
## terraform block

Блок `terraform {}` содержит настройки Terraform, включая требуемых поставщиков, которые Terraform будет использовать для предоставления вашей инфраструктуры. Для каждого поставщика атрибут source определяет необязательное имя хоста, пространство имен и тип поставщика. Terraform устанавливает поставщиков из реестра Terraform
## providers

Блок провайдера настраивает указанного провайдера, в данном случае oci. Провайдер — это плагин, который Terraform использует для создания и управления вашими ресурсами.
## resources

Используйте блоки ресурсов для определения компонентов вашей инфраструктуры. Ресурс может быть физическим или виртуальным компонентом, таким как VCN, или логическим ресурсом, таким как приложение Heroku.

# Proxmox base main.tf

```bash
terraform {
  required_version = ">= 1.1.0"
  required_providers {
    proxmox = {
      source  = "telmate/proxmox"
      version = "3.0.1-rc3"
    }
  }
}

provider "proxmox" {
  pm_tls_insecure = true
  pm_api_url      = "http://192.168.1.111:8006/api2/json"
  pm_password     = "InRazzerDeath1232"
  pm_user         = "terraform-prov@pve"
  pm_otp          = ""
}

  

resource "proxmox_vm_qemu" "cloudinit-test" {
  name        = "tftest1.xyz.com"
  desc        = "tf description"
  target_node = "homelab"
  
  clone = "debian-cloud"
  
  scsihw = "virtio-scsi-single" #controller
  os_type   = "cloud-init"
  ipconfig0 = "ip=192.168.1.200/24,gw=192.168.1.1"
  
  
  disks {
    ide { # cd-rom drive
      ide2 {
        cloudinit {
          storage = "local-lvm" 
        }
      }
    }
    scsi {
      scsi0 {
        disk {
          size         = 10
          cache        = "writeback"
          storage      = "local-lvm"
          iothread     = false 
          discard      = false
        }
      }
    }
  }
}
```

