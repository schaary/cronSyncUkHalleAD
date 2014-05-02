#!/usr/bin/env ruby
# encoding: utf-8

require 'thor'
require 'net/ldap'
require 'pry'

class SyncUkHalleAD < Thor
  desc 'fetch','fetch'
  def fetch
    connect_uk_ad
    binding.pry
  end

private
  def connect_uk_ad
    unless @ad
      @ad = Net::LDAP.new
      @ad.host = ENV.fetch('AD_UK_HALLE_HOST')
      @ad.port = 389
      @ad.encryption :simple
      @ad.auth ENV.fetch('AD_UK_HALLE_USER'), ENV.fetch('AD_UK_HALLE_PASSWORD')
    end
  end

end

SyncUkHalleAD.start
