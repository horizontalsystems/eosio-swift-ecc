using_local_pods = ENV['USE_LOCAL_PODS'] == 'true' || false

platform :ios, '11.0'

# ignore all warnings from all pods
inhibit_all_warnings!

if using_local_pods
  # Pull pods from sibling directories if using local pods
  target 'EosioSwiftEcc' do
    use_frameworks!

    target 'EosioSwiftEccTests' do
      inherit! :search_paths
      pod 'GRKOpenSSLFramework', '1.0.2.19'
      pod 'EosioSwift', :path => '../eosio-swift'
    end

    pod 'GRKOpenSSLFramework', '1.0.2.19'
    pod 'EosioSwift', :path => '../eosio-swift'
    pod 'SwiftLint'

    pod 'UIExtensions.swift', :path => '../gui-kit/'
  end
else
  # Pull pods from sources above if not using local pods
    target 'EosioSwiftEcc' do
    use_frameworks!

    target 'EosioSwiftEccTests' do
      inherit! :search_paths
      pod 'GRKOpenSSLFramework', '1.0.2.19'
      pod 'EosioSwift', git: 'https://github.com/horizontalsystems/eosio-swift'
    end

    pod 'GRKOpenSSLFramework', '1.0.2.19'
    pod 'SwiftLint'

    pod 'EosioSwift', git: 'https://github.com/horizontalsystems/eosio-swift'
    pod 'UIExtensions.swift', git: 'https://github.com/horizontalsystems/gui-kit/'
 end
end
