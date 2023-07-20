terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.0"
    }
  }
}

provider "aws" {
  region     = "us-east-1"
 }


resource "aws_instance" "s1" {
  ami           = "ami-022e1a32d3f742bd8"
  instance_type = "t2.micro"
  key_name = "${var.key_pair}"

  tags = {
    Name = "server1"
  }
}


resource "aws_instance" "s2" {
  ami           = "ami-022e1a32d3f742bd8"
  instance_type = "t2.micro"

  tags = {
    Name = "server2"
  }
}

/*
resource "aws_instance" "s3" {
  ami           = "ami-022e1a32d3f742bd8"
  instance_type = "t2.micro"

  tags = {
    Name = "server3"
  }
}
*/
