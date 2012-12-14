Vagrant::Config.run do |config|
  config.vm.box = "symfony2-phpconfbr2012"

  config.vm.box_url = "https://bitbucket.org/rogeriopradoj/symfony2-vagrant-phpconfbrasil2012/downloads/symfony2-phpconfbr2012.box"

  config.vm.network :hostonly, "192.168.56.10"

  # Faz o NFS funcionar adequadamente tanto em hosts Windows quanto nos outros hosts
  # http://happykoalas.com/blog/2012/04/vagrant-and-using-nfs-only-on-non-windows-host/
  def Kernel.is_windows?
    # Detect if we are running on Windows
    processor, platform, *rest = RUBY_PLATFORM.split("-")
    platform == 'mingw32'
  end
  nfs = !Kernel.is_windows?
  config.vm.share_folder "v-root", "/vagrant", "exemplos", :nfs => nfs

end
