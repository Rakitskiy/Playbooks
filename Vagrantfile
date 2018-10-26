# -*- mode: ruby -*-
# vi: set ft=ruby :

# Require the AWS provider plugin
require 'vagrant-aws'

# Create and configure the AWS instance(s)
Vagrant.configure('2') do |config|

  # Use dummy AWS box
  config.vm.box = 'dummy'

  # Specify AWS provider configuration
  config.vm.provider 'aws' do |aws, override|
    # Read AWS authentication information from environment variables
    aws.access_key_id = ENV['AWS_ACCESS_KEY_ID']
    aws.secret_access_key = ENV['AWS_SECRET_ACCESS_KEY']

    # Specify SSH keypair to use
    aws.keypair_name = 'TestTask'

    # Specify region, AMI ID, and security group(s)
    aws.region = 'eu-central-1'
    aws.instance_type = "t2.micro"
    aws.ami = 'ami-0bdf93799014acdc4'
    aws.security_groups = ['default']

  config.vm.synced_folder '.', '/vagrant', disabled: true
    # Specify username and private key path
    override.ssh.username = 'ubuntu'
    override.ssh.private_key_path = 'C:\Users\rakitskiy\Downloads\TestTask.pem'
  end
end
