require 'fileutils'

vim_dir = File.expand_path("~/.vim")
vim_rc  = File.expand_path("~/.vimrc")
new_vim_dir = File.expand_path(File.dirname(__FILE__))
new_vim_rc = File.join(new_vim_dir, "vimrc")

desc "Install vim configuration"
task :install do
  if File.exists?(vim_rc)
    File.delete(vim_rc)
  end
  puts "Creating link from #{vim_rc} to #{new_vim_rc}"
  File.symlink(new_vim_rc, vim_rc)

  if File.exists?(vim_dir)
    FileUtils.rm_rf(vim_dir)
  end
  puts "Creating link from #{vim_dir} to #{new_vim_dir}"
  File.symlink(new_vim_dir, vim_dir)
end

task :default => :install
